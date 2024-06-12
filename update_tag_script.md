<!--markdownlint-disable MD041-->

### Special script to update tag ###

#### To call the update_git_tag function from the shell without directly loading it into your .bashrc, you can source the script containing the function definition. Here's how you can do it ####

Save the function to a separate script file:

Create a file named update_git_tag.sh and place the update_git_tag function and its helper functions inside it. The file should look like this:

```bash
# update_git_tag.sh

# Function to extract version name from build.gradle (replace this with actual extraction logic)

extract_version_name() {
    # Placeholder function, implement your logic here
    echo "0.1.0"
}

# Function to get the latest tag (replace this with actual logic)

get_latest_tag() {
    git describe --tags `git rev-list --tags --max-count=1`
}

# Function to increment version (replace this with actual logic)

increment_version() {
    IFS='.' read -r -a parts <<< "${1#v}"
    parts[2]=$((parts[2] + 1))
    echo "v${parts[0]}.${parts[1]}.${parts[2]}"
}

update_git_tag() {
    if git rev-parse --is-inside-work-tree > /dev/null 2>&1; then
        latest_tag=$(get_latest_tag)
        echo "Latest tag: $latest_tag"

        if [[ "$latest_tag" =~ ^v?[0-9]+\.[0-9]+\.[0-9]+$ ]]; then
            # Increment the version
            new_version=$(increment_version "$latest_tag")
            git tag "$new_version"
            git push --tags
        else
            # If no tags exist, start with version in build.gradle file
            new_version=$(extract_version_name)
            git tag "$new_version"
            git push --tags
        fi

        echo "Git tag version: $new_version"
    else
        echo "Not inside a git repository."
    fi
}

```

Source the script in your shell session:

To use the update_git_tag function in your current shell session, you need to source the script file. You can do this by running:

```bash
source /path/to/update_git_tag.sh
```

Replace /path/to/ with the actual path to your script file.

Call the function:

After sourcing the script, you can call the update_git_tag function directly from your shell:

```bash
update_git_tag
```

Putting It All Together
Here are the steps in sequence:

Save the update_git_tag script to a file:

```bash
echo '   # update_git_tag.sh

# Function to extract version name from build.gradle (replace this with actual extraction logic) 

extract_version_name() {
    # Placeholder function, implement your logic here
    echo "0.1.0"
}

# Function to get the latest tag (replace this with actual logic)

get_latest_tag() {
    git describe --tags `git rev-list --tags --max-count=1`
}

# Function to increment version (replace this with actual logic)

increment_version() {
    IFS='\''.'\'' read -r -a parts <<< "${1#v}"
    parts[2]=$((parts[2] + 1))
    echo "v${parts[0]}.${parts[1]}.${parts[2]}"
}

update_git_tag() {
    if git rev-parse --is-inside-work-tree > /dev/null 2>&1; then
        latest_tag=$(get_latest_tag)
        echo "Latest tag: $latest_tag"

        if [[ "$latest_tag" =~ ^v?[0-9]+\.[0-9]+\.[0-9]+$ ]]; then
            # Increment the version
            new_version=$(increment_version "$latest_tag")
            git tag "$new_version"
            git push --tags
        else
            # If no tags exist, start with version in build.gradle file
            new_version=$(extract_version_name)
            git tag "$new_version"
            git push --tags
        fi

        echo "Git tag version: $new_version"
    else
        echo "Not inside a git repository."
    fi
}' > ~/update_git_tag.sh

```

Source the script:

```bash
source ~/update_git_tag.sh
```

Call the function:

```bash
update_git_tag
```

By following these steps, you can keep your .bashrc file clean and still use the update_git_tag function whenever needed.

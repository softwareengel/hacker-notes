---
title: 
tags: 
Date: 2024-04-04
---


# Obsidian Skript to get all Tags 

![](../_asset/2024-04-04_obsidian%20Script_image_1.jpg)


```javascript
// Retrieve all tags from the current vault
function getAllTags() {
    const tags = new Set();

    // Iterate through all files in the vault
    for (const file of app.vault.getFiles()) {
        // Get the frontmatter of each file
        const frontmatter = app.metadataCache.getFileCache(file)?.frontmatter;
        if (frontmatter) {
            // Extract tags from the frontmatter
            const fileTags = frontmatter.tags;
            if (Array.isArray(fileTags)) {
                // Add tags to the set
                fileTags.forEach(tag => tags.add(tag));
            }
        }
    }

    return Array.from(tags);
}

// Call the function to retrieve all tags and log them
const allTags = getAllTags();
console.log(allTags);
```

![](../_asset/2024-04-04_obsidian%20Script_image_2.jpg)

# 
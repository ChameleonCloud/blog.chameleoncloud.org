# Chameleon's Blog

The source for https://blog.chameleoncloud.org.

## Making a post

1. Create a new markdown file under `content/posts` and fill in the frontmatter. The `hugo` cli will help with this,
if you have it installed. Run it from the repo root directory like `hugo new content posts/2026-03-10-changelog.md`, replacing `2026-03-10-changelog` with something for your specific blog post.

2. If you want your blog post to have an image associated with it, you can upload it to ["Filer" in the django admin](https://chameleoncloud.org/admin/filer/folder/). Then, you can right click the download icon next to your uploaded file, and copy the image link. Save this under the "image" key in the frontmatter. These images will automatically be embedded in the top of the post.

3. Remove "Featured" from older blog posts.

4. You can verify your post looks good by running `hugo serve` command. 
# wp comment generate

Generate some number of new dummy comments.

Creates a specified number of new comments with dummy data.

### OPTIONS

[\--count=&lt;number&gt;]
: How many comments to generate?
\---
default: 100
\---

[\--post_id=&lt;post-id&gt;]
: Assign comments to a specific post.

[\--format=&lt;format&gt;]
: Render output in a particular format.
\---
default: progress
options:
  - progress
  - ids
\---

### EXAMPLES

    # Generate comments for the given post.
    $ wp comment generate --format=ids --count=3 --post_id=123
    138 139 140

    # Add meta to every generated comment.
    $ wp comment generate --format=ids --count=3 | xargs -d ' ' -I % wp comment meta add % foo bar
    Success: Added custom field.
    Success: Added custom field.
    Success: Added custom field.

### GLOBAL PARAMETERS

These [global parameters](https://make.wordpress.org/cli/handbook/config/) have the same behavior across all commands and affect how WP-CLI interacts with WordPress.

| **Argument**    | **Description**              |
|:----------------|:-----------------------------|
| `--path=<path>` | Path to the WordPress files. |
| `--url=<url>` | Pretend request came from given URL. In multisite, this argument is how the target site is specified. |
| `--ssh=[<scheme>:][<user>@]<host|container>[:<port>][<path>]` | Perform operation against a remote server over SSH (or a container using scheme of "docker" or "docker-compose"). |
| `--http=<http>` | Perform operation against a remote WordPress install over HTTP. |
| `--user=<id|login|email>` | Set the WordPress user. |
| `--skip-plugins[=<plugin>]` | Skip loading all or some plugins. Note: mu-plugins are still loaded. |
| `--skip-themes[=<theme>]` | Skip loading all or some themes. |
| `--skip-packages` | Skip loading all installed packages. |
| `--require=<path>` | Load PHP file before running the command (may be used more than once). |
| `--[no-]color` | Whether to colorize the output. |
| `--debug[=<group>]` | Show all PHP errors; add verbosity to WP-CLI bootstrap. |
| `--prompt[=<assoc>]` | Prompt the user to enter values for all command arguments, or a subset specified as comma-separated values. |
| `--quiet` | Suppress informational messages. |
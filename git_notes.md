# Git learning notes

- git init

<div class="verseblock">
<pre class="content"><code>git init</code> [<code>-q</code> | <code>--quiet</code>] [<code>--bare</code>] [<code>--template=</code><em>&lt;template-directory&gt;</em>]
	  [<code>--separate-git-dir</code> <em>&lt;git-dir&gt;</em>] [<code>--object-format=</code><em>&lt;format&gt;</em>]
	  [<code>--ref-format=</code><em>&lt;format&gt;</em>]
	  [<code>-b</code> <em>&lt;branch-name&gt;</em> | <code>--initial-branch=</code><em>&lt;branch-name&gt;</em>]
	  [<code>--shared</code>[<code>=</code><em>&lt;permissions&gt;</em>]] [<em>&lt;directory&gt;</em>]</pre>
</div>

- git config
```
git config --list # view all variables set of config file
git config [get] <key>  # view key option set

git config --global [set] <key> <value> # user level set
git config --system [set] <key> <value> # system level set
git config [set] <key> <value>          # repository level set

```


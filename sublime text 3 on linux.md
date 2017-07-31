sublime text 3 on Ubuntu 16.04 lts:

1. How to deal with Chinese here?
	+ [solution for Chinese input][]
	```
		git clone https://github.com/lyfeyaj/sublime-text-imfix.git
		cd sublime-text-imfix
		./sublime-imfix
	```
	+ Change the font_face so  Chinese and English could work together friendly
		`"font_face":"YaHei Consolas Hybrid"`or`"font_face":"Microsoft YaHei"`
		You have to install it before you use it, [source for the font][]

2. the essential plug-ins to make the st a better text editor to use
	+ basic
		- Package Control
			It is easy to install it with `Ctrl+shift+p`
		- BracketHighlighter
			auto hightlight  bracket in various source files.
	+ Markdown
		- Markdown extend + Monokai extended
			* description: this is  a highlight color scheme for markdown writing
			* setting: Preference --> ColorScheme --> MonokaiExtended
		- Markdown preview
	    		* description: this is to preview your markdown file as html
	    		* setting: add a short cut if you want
	    			example:`{ "keys": ["alt+m"], "command": "markdown_preview", "args": {"target": "browser", "parser":"markdown"} }`
	+ Python
	[blog][]---really a nice blog.
		-  plugin Sublime Repel
			`Solve the problem that we can not input with python`
			*  python3
				Preferences----> Browse Packages ---->SublimeREpel ----> create a folder name `python3.5`---->create two files`Default.sublime-commands`and`Main.sublime.menu`
				[some description for these two files][]
				`These two files you could just modify those in *python* folder`
			* shortcut
				Preferences---->Keybindings---->create your own shortcut
				`You name your keys and copy the command from the Default.sublime-commands file`
		- plugin Anaconda
			`make sublime text3 more IDE-like  `
	+ git
		- Sublime Git


3. build c/c++ files in sublime text3
`for linux only, you have to do something more on windows`
Tools--->Build System--->New Build System
```
{
	"cmd" : ["gcc", "$file_name", "-o", "${file_base_name}", "-lm", "-Wall"],
	"file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
	"selector" : "source.c, source.c++",
	"shell":false,
	"working_dir" : "$file_path",

	"variants":
	[
		{
			"name": "Run",
			"cmd": ["gnome-terminal", "-e", "bash -c \"gcc '${file}' -o '${file_path}/${file_base_name}' -lm -Wall && '${file_path}/${file_base_name}' ; read -p '\nPress any key to continue...'\""]
	 	}
	]
}
```


4. Backup and  regain the configuration with git
`here you just back up the configuration but not the packages itself, so you have to install them again from scratch `
[Backup guide blog][]






[solution for Chinese input]:http://www.jianshu.com/p/bf05fb3a4709
[source for the font]:https://github.com/cypro666/yahei.consolas-font
[blog]:http://www.cnblogs.com/unflynaomi/p/5704293.html
[some description for these two files]:https://sublimerepl.readthedocs.io/en/latest/
[Backup guide blog]:http://zuyunfei.com/2015/05/21/backup-sublime-settings/

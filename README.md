Sublime Text 2 & 3 plugin that makes vintage mode close the completion menu and enter normal mode when escape is pressed.


Default key bindings:

	{ "keys": ["escape"], "command": "exit_auto_complete_and_insert_mode", "context":
		[
			{ "key": "auto_complete_visible", "operator": "equal", "operand": true }
		]
	},

	{ "keys": ["ctrl+["], "command": "exit_auto_complete_and_insert_mode", "context":
		[
			{ "key": "auto_complete_visible", "operator": "equal", "operand": true }
		]
	},


The entire plugin consists of:

	import sublime_plugin
	class ExitAutoCompleteAndInsertMode(sublime_plugin.TextCommand):
		def run(self, edit):
			self.view.run_command("hide_auto_complete")
			self.view.run_command("exit_insert_mode")
  

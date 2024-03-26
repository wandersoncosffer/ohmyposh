{
  "$schema": "https://raw.githubusercontent.com/JanDeDobbeleer/oh-my-posh/main/themes/schema.json",
  "blocks": [
    {
      "alignment": "left",
      "segments": [
        {
          "background": "#f36943",
          "foreground": "#ffffff",
          "leading_diamond": "",
          "style": "diamond",
          "template": " {{ .UserName }} ",
          "trailing_diamond": "",
          "type": "session"
        },
        {
          "background": "#FFAF45",
          "foreground": "#ffffff",
          "powerline_symbol": "",
          "properties": {
            "folder_separator_icon": "  ",
            "home_icon": "~",
            "style": "folder"
          },
          "style": "powerline",
          "template": "   {{ .Path }} ",
          "type": "path"
        },
        {
          "background": "#fffb38",
          "background_templates": [
            "{{ if or (.Working.Changed) (.Staging.Changed) }}#FF9248{{ end }}",
            "{{ if and (gt .Ahead 0) (gt .Behind 0) }}#ff4500{{ end }}",
            "{{ if gt .Ahead 0 }}#B388FF{{ end }}",
            "{{ if gt .Behind 0 }}#B388FF{{ end }}"
          ],
          "foreground": "#193549",
          "leading_diamond": "",
          "powerline_symbol": "",
          "properties": {
            "branch_max_length": 25,
            "fetch_stash_count": true,
            "fetch_status": true,
            "fetch_upstream_icon": true
          },
          "style": "powerline",
          "template": " {{ .UpstreamIcon }}{{ .HEAD }}{{if .BranchStatus }} {{ .BranchStatus }}{{ end }}{{ if .Working.Changed }}  {{ .Working.String }}{{ end }}{{ if and (.Working.Changed) (.Staging.Changed) }} |{{ end }}{{ if .Staging.Changed }}  {{ .Staging.String }}{{ end }}{{ if gt .StashCount 0 }}  {{ .StashCount }}{{ end }} ",
          "trailing_diamond": "",
          "type": "git"
        },
        {
          "background": "#6CA35E",
          "foreground": "#ffffff",
          "powerline_symbol": "",
          "properties": {
            "fetch_version": true
          },
          "style": "powerline",
          "template": "  {{ if .PackageManagerIcon }}{{ .PackageManagerIcon }} {{ end }}{{ .Full }} ",
          "type": "node"
        },
        {
          "background": "#8ED1F7",
          "foreground": "#111111",
          "powerline_symbol": "",
          "properties": {
            "fetch_version": true
          },
          "style": "powerline",
          "template": "  {{ if .Error }}{{ .Error }}{{ else }}{{ .Full }}{{ end }} ",
          "type": "go"
        },
        {
          "background": "#4063D8",
          "foreground": "#111111",
          "powerline_symbol": "",
          "properties": {
            "fetch_version": true
          },
          "style": "powerline",
          "template": "  {{ if .Error }}{{ .Error }}{{ else }}{{ .Full }}{{ end }} ",
          "type": "julia"
        },
        {
          "background": "#FFDE57",
          "foreground": "#111111",
          "powerline_symbol": "",
          "properties": {
            "display_mode": "files",
            "fetch_virtual_env": false
          },
          "style": "powerline",
          "template": "  {{ if .Error }}{{ .Error }}{{ else }}{{ .Full }}{{ end }} ",
          "type": "python"
        },
        {
          "background": "#AE1401",
          "foreground": "#ffffff",
          "powerline_symbol": "",
          "properties": {
            "display_mode": "files",
            "fetch_version": true
          },
          "style": "powerline",
          "template": "  {{ if .Error }}{{ .Error }}{{ else }}{{ .Full }}{{ end }} ",
          "type": "ruby"
        },
        {
          "background": "#FEAC19",
          "foreground": "#ffffff",
          "powerline_symbol": "",
          "properties": {
            "display_mode": "files",
            "fetch_version": false
          },
          "style": "powerline",
          "template": " {{ if .Error }}{{ .Error }}{{ else }}{{ .Full }}{{ end }} ",
          "type": "azfunc"
        },
        {
          "background_templates": [
            "{{if contains \"default\" .Profile}}#FFA400{{end}}",
            "{{if contains \"jan\" .Profile}}#f1184c{{end}}"
          ],
          "foreground": "#ffffff",
          "powerline_symbol": "",
          "properties": {
            "display_default": false
          },
          "style": "powerline",
          "template": "  {{ .Profile }}{{ if .Region }}@{{ .Region }}{{ end }} ",
          "type": "aws"
        },
        {
          "background": "#ffff66",
          "foreground": "#111111",
          "powerline_symbol": "",
          "style": "powerline",
          "template": "  ",
          "type": "root"
        },
        {
          "background": "#D74B76",
          "foreground": "#ffffff",
          "properties": {
            "always_enabled": true
          },
          "style": "plain",
          "template": "<transparent></>  {{ .FormattedMs }}⠀",
          "type": "executiontime"
        },
        {
          "background": "#673F69",
          "background_templates": [
            "{{ if gt .Code 0 }}#e91e63{{ end }}"
          ],
          "foreground": "#ffffff",
          "properties": {
            "always_enabled": true
          },
          "style": "diamond",
          "template": "<parentBackground></>  ",
          "trailing_diamond": "",
          "type": "status"
        }
      ],
      "type": "prompt"
    },
    {
      "segments": [
        {
          "background": "#0077c2",
          "foreground": "#ffffff",
          "style": "plain",
          "template": "<#0077c2,transparent></>  {{ .Name }} <transparent,#0077c2></>",
          "type": "shell"
        },
        {
          "background": "#1BD760",
          "foreground": "#111111",
          "invert_powerline": true,
          "powerline_symbol": "",
          "properties": {
            "paused_icon": " ",
            "playing_icon": " "
          },
          "style": "powerline",
          "template": "  {{ .Icon }}{{ if ne .Status \"stopped\" }}{{ .Artist }} - {{ .Track }}{{ end }} ",
          "type": "ytm"
        },
     
        {
          "background": "#FFD23F",
          "foreground": "#111111",
          "invert_powerline": true,
          "leading_diamond": "",
          "style": "diamond",
          "template": " {{ .CurrentDate | date .Format }} ",
          "trailing_diamond": "",
          "type": "time"
        }
      ],
      "type": "rprompt"
    }
  ],
  "console_title_template": "{{ .Shell }} in {{ .Folder }}",
  "final_space": true,
  "version": 2
}

# funcionalidades
Funcionalidades para a Assistente Virtual AVA.
No momento: migrando para submodules e realizando testes

# Instalação
---

Os nomes das skills em DEFAULT-SKILLS devem ter o mesmo nome que os adicionados em submódulos.

```
  "skills": {
    "msm": {

      // Relative to "data_dir"
      "directory": "skills",
      "versioned": true,

      "repo": {
        // Relative to "data_dir"
        "cache": ".skills-repo",
        "url": "https://github.com/rafaeldefazio/funcionalidades",
        "branch": "master"
      }
    },

    "upload_skill_manifest": true,

    // Directory to look for user skills
    "directory": "~/.mycroft/skills",

    // Enable auto update by msm
    "auto_update": true,

    // blacklisted skills to not load
    // NB: This is the basename() of the directory where the skill lives, so if
    // the skill you want to blacklist is in /opt/mycroft/skills/mycroft-alarm.mycroftai/
    // then you should write "mycroft-alarm.mycroftai" below.
    "blacklisted_skills": ["skill-media", "send_sms", "skill-wolfram-alpha", "pianobar-skill"],

    // priority skills to be loaded first
    "priority_skills": ["mycroft-pairing", "mycroft-volume"],
    
    // Time between updating skills in hours
    "update_interval": 1.0
  }
  ```
  
## Force a reinstalação de dependências

1. Apague o arquivo `/home/mycroft/.mycroft/.mycroft-skill`
1. Apague o arquivo `/opt/mycroft/skills/.msm`
1. Reinicie o serviço de skills, mycroft-skills, utilizando o comando `sudo service mycroft-skills restart`

```sh
source venv-activate.sh
mycroft-config reload
```


### Frappe bench

> contains all configurations

```bash
╭─frappe@custom.inxeoz.com ~/frappe-bench
╰─➤  tree -L 1
.
├── apps
├── config
├── env
├── logs
├── patches.txt
├── Procfile
└── sites
```

### apps

> contains all applications
>
> ```
> ╭─frappe@custom.inxeoz.com ~/frappe-bench/apps
> ╰─➤  tree -L 1
> apps
> ├── custom_booking
> └── frappe
> ```
> 
> 

### config

> frappe generated config

### env

> python environment that frappe uses

###  logs

> all the logs generated frappe

### patches.text

> all the list of patches that was applied 

### procfile

> Defines how bench runs in production

### sites

> contains sites global configuration and site it self here
>
> ```bash
> 2 directories, 3 files
> ╭─frappe@custom.inxeoz.com ~/frappe-bench/sites
> ╰─➤  tree -L 2
> sites
> ├── apps.json
> ├── apps.txt
> ├── assets
> │   ├── assets.json
> │   ├── assets-rtl.json
> │   ├── css
> │   ├── custom_booking -> /workspace/frappe-bench/apps/custom_booking/custom_booking/public
> │   ├── frappe -> /workspace/frappe-bench/apps/frappe/frappe/public
> │   ├── js
> │   └── locale
> ├── common_site_config.json
> └── custom.inxeoz.com
>     ├── locks
>     ├── logs
>     ├── private
>     ├── public
>     ├── site_config.json
>     └── touched_tables.json
> 
> ```

---

---

### sites/apps.json

> contains application commit hash and github branch if it is from github
>
> ```
> {
>     "frappe": {
>         "resolution": {
>             "commit_hash": null,
>             "branch": null
>         },
>         "required": [],
>         "idx": 1,
>         "version": "15.87.0"
>     },
>     "custom_app": {
>         "is_repo": true,
>         "resolution": {
>             "commit_hash": "shdskjfhdsfsddsfshdf",
>             "branch": "develop"
>         },
>         "required": [],
>         "idx": 2,
>         "version": "0.0.1"
>     }
> }
> ```
>
> 

### sites/apps.txt

> list of application
>
> ```bash
> ╭─frappe@custom.inxeoz.com ~/frappe-bench/sites
> ╰─➤  cat apps.txt
> frappe
> custom_app                                                                                                                         
> ```



### sites/assets

>contains frontend build of application (symlink to be exact)
>
>```bash
>╭─frappe@custom.inxeoz.com ~/frappe-bench/sites/assets
>╰─➤  tree -L 1
>assets
>├── assets.json
>├── assets-rtl.json
>├── css
>├── custom_booking -> /workspace/frappe-bench/apps/custom_booking/custom_booking/public
>├── frappe -> /workspace/frappe-bench/apps/frappe/frappe/public
>├── js
>└── locale
>```

### sites/common_site_config.json

>contains global information for sites like setting ``bench set-config -g key value`` with ``-g`` updates here
>
>```
>{
>  "background_workers": 1,
>  "db_host": "global-db",
>  "db_port": 3306,
>  "default_site": "custom.inxeoz.com",
>  "developer_mode": true,
>  "dns_multitenant": true,
>  "file_watcher_port": 6787,
>  "frappe_user": "frappe",
>  "gunicorn_workers": 9,
>  "install_apps": [],
>  "live_reload": true,
>  "rebase_on_pull": false,
>  "redis_cache": "redis://fm__custom_inxeoz_com__redis-cache:6379",
>  "redis_queue": "redis://fm__custom_inxeoz_com__redis-queue:6379",
>  "redis_socketio": "redis://fm__custom_inxeoz_com__redis-cache:6379",
>  "restart_supervisor_on_update": true,
>  "restart_systemd_on_update": false,
>  "serve_default_site": true,
>  "shallow_clone": true,
>  "socketio_port": 80,
>  "use_redis_auth": false,
>  "webserver_port": 80
>}
>```

---

---

### sites/custom.inxeoz.com

>contains all information (configuration ) related to site
>
>```
>╭─frappe@custom.inxeoz.com ~/frappe-bench/sites/custom.inxeoz.com
>╰─➤  tree -L 1
>custom.inxeoz.com
>├── locks
>├── logs
>├── private
>├── public
>├── site_config.json
>└── touched_tables.json
>```

### sites/custom.inxeoz.com/locks

### sites/custom.inxeoz.com/logs

### sites/custom.inxeoz.com/private

> contains backup file sql file
>
> ```
> ╭─frappe@custom.inxeoz.com ~/frappe-bench/sites/custom.inxeoz.com/private
> ╰─➤  tree -L 1
> private
> ├── backups
> └── files
> ```

### sites/custom.inxeoz.com/public

### sites/custom.inxeoz.com/site_config.json

>contains configuration details of site like db credentials 
>
>and configs that is set by ``bench set-config key value`` without using ``-g``
>
>```
>{
> "admin_password": "windwos",
> "db_host": "global-db",
> "db_name": "custom-inxeoz-com",
> "db_password": "windwosBEh",
> "db_port": 3306,
> "db_type": "mariadb",
> "hello": "word"
>}
>```
>
>

### sites/custom.inxeoz.com/touched_tables.json

> contains list of database tables that is created or modified by frappe for site
>
> ```
> [
>     "tabProperty Setter",
>     "tabSlot Table",
>     "tabWorkflow Action Permitted Role",
>     "tabClient"
>     
>  ]
> ```

---

---

### apps/custom_booking

```
╭─frappe@custom.inxeoz.com ~/frappe-bench/apps/custom_booking  ‹develop*›
╰─➤  tree -L 5

custom_booking/
├── custom_booking/
│   ├── config/
│   ├── custom_booking/
│   │   ├── doctype/
│   │   │   ├── api/
│   │   │   ├── approver/
│   │   │   ├── attender/
│   │   │   ├── companion_table/
│   │   │   ├── devoteee/
│   │   │   │   ├── devoteee.json
│   │   │   │   ├── devoteee.js
│   │   │   │   └── devoteee.py
│   │   │   ├── ... many doctypes ...
│   ├── fixtures/
│   ├── hooks.py
│   ├── modules.txt
│   ├── patches.txt
│   ├── public/
│   └── templates/
├── license.txt
├── pyproject.toml
└── README.md

```



> dont confuse yourself by three custom_booking (each has its own meaning)

```
frappe-bench/
└── apps/
    └── custom_booking/          ← The app folder (bench level)
        └── custom_booking/      ← The Python package (custom app name)
            └── custom_booking/  ← The module

```

>doctype folder contains all the doctype, a doctype which created with
>
>Module = custom_booking
>
>Custom? = **Unchecked** (Because Checked would create doctype in database and not map in source code )

```

custom_booking/
├── custom_booking/
│   ├── config/
│   ├── custom_booking/
│   │   ├── doctype/					← Doctype folder
│   │   │   ├── api/
│   │   │   ├── approver/
│   │   │   ├── attender/
│   │   │   ├── companion_table/
│   │   │   ├── devoteee/				← Doctype
│   │   │   │   ├── devoteee.json		← Json file represent the devoteee doctype schema
│   │   │   │   ├── devoteee.js			← js file that controls that devoteee frappe ui
│   │   │   │   └── devoteee.py			← py file that handles backend control like validation

```


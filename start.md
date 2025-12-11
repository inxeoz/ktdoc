# What is Frappe Framework?[ ](https://docs.frappe.io/framework/user/en/basics#what-is-frappe-framework)

Frappe is a full stack, batteries-included, web framework written in Python and Javascript.

It is the framework which powers [ERPNext](https://erpnext.com/). It is pretty generic and can be used to build database driven apps.

> https://docs.frappe.io/framework/user/en/basics



#### So Whats in it

> Doctypes ( similar to form )

> Workflow (enable flow of form from role to role i.e user to authority)

> Client Script (Manages ui Interaction in frappe frontend)

> Server Script (Manages Backend using python - frappe scripts i.e validation, api servering)



### How to work with frappe framework

> Using Docker https://github.com/frappe/frappe_docker

> Using Wsl (linux)



## WSL (linux : Ubuntu)

### Setup wsl windows os 

https://learn.microsoft.com/en-us/windows/wsl/install



1. ```wsl --install --web-download```
2. ```wsl --install``` it will install ubuntu 
3. ```wsl  -d ubuntu``` to login into ubuntu wsl instance (First Login will ask for user-name and password)
4. after login goto home dir ```cd ~```

## setup frappe bench in ubuntu linux (or Wsl Ubuntu)

### Installing Packges

1. ```sudo apt update``` ***update packges***

2. ```sudo apt install git python-is-python3 python3-dev python3-pip redis-server libmariadb-dev mariadb-server mariadb-client pkg-config``` ***install required services***

3. ```sudo apt install xvfb libfontconfig```

4. ```sudo mariadb-secure-installation``` ***it will ask for root password to authorize and ask for new-password for mariadb (if you have not setup this before)***

5. Install Node and Yarn (https://nodejs.org/en/download)

   > Get Node.js® (**V24...lts**) for (**Linux**) Using (**nvm**) With (**Yarn**)

   >```bash
   ># Download and install nvm:
   >curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
   >
   ># in lieu of restarting the shell
   >\. "$HOME/.nvm/nvm.sh"
   >
   ># Download and install Node.js:
   >nvm install 24
   >
   ># Verify the Node.js version:
   >node -v # Should print "v24.11.1".
   >
   ># Download and install Yarn:
   >corepack enable yarn
   >
   ># Verify Yarn version:
   >yarn -v
   >```

​	this will install node and yarn both

### Setup Python Env

1. ```python --version``` ***check python version***
2. ```sudo apt install python3.10-venv``` ***if python version is 3.10***
3. ```python -m venv frappe-env``` ***creating python environment***
4. ```source frappe-env/bin/activate``` ***sourcing the env***

### Bench Setup

1. ```pip install frappe-bench```  ***installing frappe-bench (we will use this to work with frappe-framework)***

2. ```bench init prob```  ***creating bench folder that contains all the configuration and setup of bench / sites /  apps***

3. ```cd prob```  ***directory where from where bench commands can be applied***

4. ```bench new-site frontend``` ***it will asks for super-user and mysql root password***

5. ```bench use frontend``` ***this will set site to frontend***

6. ```bench start```  ***this will start the site***

   > ```bash
   > 
   > …/2025-12-05-test/prob ✗ bench start
   > 15:03:03 system        | redis_queue.1 started (pid=52053)
   > 15:03:03 system        | redis_cache.1 started (pid=52050)
   > ---------------------------------------------------
   > ---------------------------------------------------
   > 15:03:04 web.1         |  * Running on all addresses (0.0.0.0)
   > 15:03:04 web.1         |  * Running on http://127.0.0.1:8000
   > 15:03:04 web.1         |  * Running on http://10.120.10.245:8000
   > 15:03:04 web.1         | Press CTRL+C to quit
   > ----------------------------------------------------
   > ----------------------------------------------------
   > 15:03:11 watch.1       | Watching for changes...
   > ```

   visit http://127.0.0.1:8000

### Basic Bench Commands

---

**```bench init bench_name```**

this commands create bench configuration and folder containing it

---

**```bench new-site sitename```**

creates new site and a site can have multiple selected apps and each site configuration and data does not cross

---

**```bench use sitename```**

to set default site from list of sites 

---

**```bench start```**

to start site , it starts frappe backend and frontend 

---

**```bench build```**

to generate assets of site , apps that frappe will serve

---

**``bench get-app app_name``**

to get frappe official product application i.e. (erpnext, hrms, wiki)  

to get custom application use

**```bench get-app github_repo_url```**

---

**``bench install-app app_name``**

to install app into site , use --site site_name to specify site where app will be installed

---

**```bench new-app customapp```**

to create custom app (where you can define , custom doctype and control apis)

---

**```bench drop-site sitename```**

to remove site  (be cautious it will delete all data related to site)

---

**```bench uninstall-app appname```**

to uninstall app from site , you can use --site sitename

---

**``bench export-fixtures``**

to export configurations and records for doctypes

you have to define what need to export using ``frappe-bench/apps/app_name/module_name/hooks.py``

running command will generate fixtures folder ``frappe-bench/apps/app_name/module_name/fixtures``

fixtures folder will contain json files for each records and configuration

---

**``bench migrate``**

to restore data and configuration that is inside fixtures folder ``frappe-bench/apps/app_name/module_name/fixtures``

---

**``bench set-config config_name config_value``**

to set config like ``bench set-config developer_mode 1`` or ``bench set-config server_script_enabled true```

you can use ``-g`` to set globally

---


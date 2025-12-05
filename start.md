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

### Bench Commands

```bench init```

```bench start```

```bench build```

```bench new-site sitename```

```bench new-app customapp```

```bench drop-site sitename```

```bench uninstall-app appname```

```bench get-app app_name``` ***replace app_name with frappe official apps like erpnext or non_profit, or if you have developed your own custom app then put custom app github url***

```bench install-app app_name``` ***to install app in site , you can use ```--site sitename``` to specify site***

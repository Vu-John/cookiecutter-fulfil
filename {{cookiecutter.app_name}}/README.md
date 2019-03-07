<a href="https://fulfil.io/">
    <img src="https://cdn.fulfil.io/assets/logo/full-transparent.png" alt="Fulfil.IO" title="Fulfil.IO" align="right" height="60" />
</a>

# {{ cookiecutter.project_name }}

{{ cookiecutter.project_short_description }}

## Table of content

- [Quickstart](#quickstart)
- [Environment Variables](#environment_variables)
- [Migrations](#migrations)
- [Shell](#shell)

## Quickstart

Run the following commands to bootstrap your environment:

```sh
    git clone <app-url>
    cd {{ cookiecutter.app_name }}
    pip install -r requirements.txt
```

### **How to create an App on Auth Server?**

1. Visit [Auth Service](https://auth.fulfil.io/user/)
2. Click on "View Apps" which take you [client's page](https://auth.fulfil.io/user/clients). You can see your apps listed here.
3. Click on "Create App", it will open up a form asking you about App name and App description. Just provide the name(e.g: <My-very-cool-first-app>)
4. Hit "Save". You will now see 2 more sections appear.
5. Under the "URLs" section, in Whitelisted redirection URL(s) textbox add "<http://<app-name>>.localtest.me:5000/authorized>"
6. Hit "Save"
7. That's it, you have successfully created an App
8. Under the "App Credentials", you can find your  `API Client ID` and  `API Client Secret`. Save them as `FULFIL_APP_ID` and `FULFIL_APP_SECRET` in your "environment.sh" file respectively.

## Environment Variables:

  **Note**: Read the environment variables before setting them up. Some of them will require your inputs

  ```bash
  export FLASK_APP=/path/to/manage.py
  export FULFIL_APP_ID=<The API Client ID from the App which you created in the first step>
  export FULFIL_APP_SECRET=<The API Client Secret from the App which you created in the first step>
  export REDIS_URL=redis://localhost:6379/0
  export AMQP_URL=
  export ENV=dev
  export OAUTHLIB_INSECURE_TRANSPORT=1
  export DATABASE_URI=postgresql://<your-user-name>@localhost/bifrost
  export {{ cookiecutter.app_name|upper }}_SECRET_KEY='something-really-secret'
  export ENCR_KEY=An encryption key for encrypted fields
  ```

## Migrations

Whenever a database migration needs to be made. Run the following commands:

```sh
    make migrate
```
Once you have installed your DBMS, run the following to create your app's
database tables and perform the initial migration:

  - If you are using Mac, please install GNU-SED to make the above command successful. RUN `brew install gnu-sed --with-default-names` to install.

## Shell


To open the interactive shell, run:

```sh
    flask shell
```

By default, you will have access to the flask ``app``.

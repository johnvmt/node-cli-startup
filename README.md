# node-cli-startup
Generic app CLI start script

## Example

    const startConfiguredApp = async (options) => {
        console.log(options);
    }
    
    (async () => {
        await cliStartup(startConfiguredApp, {
            cliOptions: [
                // Database
                {name: "db-url", envvar: "app_db_url", description: "Database connect string", type: String},
                {name: "db-host", envvar: "app_db_host", description: "Database host", type: String},
                {name: "db-port", envvar: "app_db_port", description: "Database port", type: Number},
                {name: "db-user", envvar: "app_db_user", description: "Database username", type: String},
                {name: "db-password", envvar: "app_db_password", description: "Database password", type: String},
                {name: "db-database", envvar: "app_db_database", description: "Database", type: String},
                {name: "db-schema", envvar: "app_db_schema", default: "public", description: "Database schema", type: String},
                {name: "db-pool", envvar: "app_db_pool", default: false, description: "Use client pool?", type: Boolean},
                {name: "db-pool-max", envvar: "app_db_pool_max", description: "Maximum clients in pool", type: Number}
            ],
            packageInfo: "package.json"
        });
    })();
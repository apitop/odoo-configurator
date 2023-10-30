/usr/src/odoosrc/apitop/odoo-configurator/main/start_config.py /usr/src/odoosrc/apitop/odoo-configurators-apitop/16.0/sfa-ibs.trial.yml

nécessite : pip3 install hiyapyco,unidecode,bs4,pykeepass,cryptocode

mettre les identifiants de connection directemnent dans le yml principal

Pour l'instant :
symfodev-sfa-group-staging-10212674.dev.odoo.com.yml fonctionne
mais pas
sfa-ibs.trial.yml alors que j'ai tout bon et que j'avais vu que le configurator marchait aussi sur mes intances
(il n'utilise que https, donc il passe bien à travers mon proxy)


Pour l'instant, j'essaie avec le mot de passe sans encodage : celui qui marche quand je me connecte à la console
et j'ai 
xmlrpc.client.ProtocolError: <ProtocolError for sfa-ibs.trial.apitop.fr//xmlrpc/2/common: 404 NOT FOUND>


il lance /usr/src/odoosrc/apitop/odoo-configurator/main/src/odoo_configurator/__main__.py

le premier argument devient l'argument 'file' dans le args = parser.parse_args()

params de lancement :
odoo_params : vient de self.config['auth']['odoo']
            odoo_params['url'],
            odoo_params['dbname'],
            odoo_params['username'],
            odoo_params['password'],
            version=self.config.get('version', False),
            http_user=odoo_params.get('http_user'),
            http_password=odoo_params.get('http_password'),
            createdb=odoo_params.get('create_db'),
            debug_xmlrpc=self.debug_xmlrpc,
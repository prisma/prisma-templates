# prisma-templates
Prisma templates for major cloud providers.

WIP.

## How to connect the Prisma CLI to your custom cluster
* Install the Prisma CLI, e.g.: `npm install -g prisma`
* Edit the Prisma config, located at `~/.prisma/config.yml` (if not present, create it).
* Add an additional entry under `clusters`, for example:
```
clusters:
  my-test-cluster:
    host: http://the-URL-to-your-cluster-endpoint.com
    clusterSecret: "Your RSA private key"
```
* When you `prisma deploy` a service, select the name you chose for the entry above. Your service will now be deployed to your cluster.

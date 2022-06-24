Installing FaxTrack is easy provided the guides are followed fully. Please take note of the below requirements for FaxTrack.

- Linux (Ubuntu) machine to operate. Commonly known as a VPS or dedicated box
- Domain name

:::info
This is a Node.Js based website and requires a server to be ran. This will not run on common 'Shared Hosting' plans.
:::

### Step One

Complete the install of a LEMN stack if you have not done so before.

- [Install a LEMN Stack](/c/knowledgebase/lemn-stack-install)

### Step Two

Now upload your FaxTrack files into a new directory on the machine under `/home/faxtrack`.

Install the database by logging into MySQL.

:::info
Use `mysql -u root -p` to login to MySQL
:::

Now in MySQL run `source /home/faxtrack/installme.sql` to install the MySQL database.

Leave the MySQL console by using `exit`.

### Step Three

Edit the config.json file located at `/home/faxtrack/config.json`

Then open a new [screen session](https://docs.faxes.zone/c/knowledgebase/screen).

Now run the below commands to get FaxTrack started.

```
cd /home/faxtrack

npm install

node .
```

FaxTrack will now be started and running.

Go to the `/setup` URL to complete the setup of FaxTrack.

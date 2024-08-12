# Bastille-scrutiny
FreeBAD Jail Template for Scrutiny, it is a Hard Drive Health Dashboard &amp; Monitoring solution, merging manufacturer provided S.M.A.R.T metrics with real-world failure rates.

Install Vaultwarden in a FreeBSD Jail environment
Installation overview using XigmanasNAS Bastille Extension Gui

## Jail Setup
1. From the main screen select Extension/Bastille
2. Click ADD [+] button
3. Name (any name will work): scrutiny
4. Configure Network Properties to your liking
5. Base Release: 13.3-Release (or newer)
6. Jail Type:  
- [ ] Create a thick container.
- [x] Enable VNET(VIMAGE). `depands on your specific network choice`
- [ ] Create an empty container.
- [x] Start after creation.
- [x] Auto start on boot.
7. Click Create
8. Click Save
9. Restart the jail.


## Applying the Scrutiny template to the newly created jail

1. SSH to your Xigmanas Server
2. BOOTSTRAP the template
`bastille bootstrap https://github.com/DarkenLight/Bastille-scrutiny`
3. Apply the Template to the TARGATE jail.
`bastille template scrutiny DarkenLight/Bastille-scrutiny`

## Applying the Scrutiny template to the newly created jail

1. make a scripts or binary dataset if not already done for other scripts (highly recomemded)
2. download the scrutiny-collector binary file. both version works, one from the same release another from current release (recomemded). 
   `https://github.com/AnalogJ/scrutiny/releases/download/0.3.13/scrutiny-collector-metrics-freebsd-amd64`
   
   `https://github.com/AnalogJ/scrutiny/releases/download/0.8.1/scrutiny-collector-metrics-freebsd-amd64`
4. Keep the file persistent storage.

   ex: `/mnt/pool/script/scrutny/scrutiny-collector-metrics-freebsd-amd64`
6. make sure the Scrutiny collector is executable. `chmod +x /mnt/pool/script/scrutny/scrutiny-collector-metrics-freebsd-amd64`
7. this command will manually trigger the collector, to populate the Scrutiny dashboard. 8080 is default port.

   `/mnt/pool/services/scrutiny/scrutiny-collector-metrics-freebsd-amd64 run --api-endpoint "http://<jail-ip>:8080"`
9. create a cron job to do it automatically

## Thanks to Scrutiny Developers
https://github.com/AnalogJ/scrutiny


# Bastille-Scrutiny
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


## Applying the Vaultwarden template to the newly created jail

1. SSH to your Xigmanas Server

2. BOOTSTRAP the template
`bastille bootstrap https://github.com/DarkenLight/Bastille-Scrutiny`

3. Apply the Template to the TARGATE jail.
`bastille template scrutiny DarkenLight/Bastille-Scrutiny`


## Thanks to Scrutiny Developers
https://github.com/AnalogJ/scrutiny


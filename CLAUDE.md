# CLAUDE.md

<!-- BEGIN .temp-kansio: hallinnoi open-desk-infra/workstations/WSL2/playbooks/05-repo-temp-symlinks.yml -->

## `.temp`-kansio

- `.temp` on repon paikallinen työkansio (esim. asennusten työtiedostot, dumpit ja viennit). Se ei ole gitissä (`.gitignore`), joten sen sisältöä ei palauteta kloonauksella
- JUKKAASUS-työaseman WSL:ssä `.temp` on symlinkki datalevylle: `.temp` → `/mnt/wsl/wsl-data/.temp/root/projects/omply/omply-public`
- Fyysisesti tiedostot ovat datalevyllä `/mnt/wsl/wsl-data` (Windowsissa `C:\WSL-DATA\wsl-data.vhdx`), eivät WSL:n päälevyllä. Datalevy varmuuskopioidaan harvemmin kuin päälevy
- Jos `.temp` näkyy tyhjänä tai rikkinäisenä linkkinä, datalevyä ei ole liitetty (esim. `wsl --shutdown`in jälkeen). Liitä se: `cd /root/projects/opendesk/open-desk-infra/workstations/WSL2/playbooks && ansible-playbook -i inventory.ini 02-mount-wsl-disks.yml`
- Älä korvaa symlinkkiä tavallisella kansiolla. Jos `.temp` puuttuu, luo se samalla mallilla: kansio datalevylle, symlinkki, `.temp` `.gitignore`:en ja tämä kuvaus tähän tiedostoon. Kaikille repoille kerralla: `ansible-playbook -i inventory.ini 05-repo-temp-symlinks.yml -e dry_run=false`
- Lisätiedot: `open-desk-infra/workstations/WSL2/README-WSL2-Levytila.md`, osio "Lisälevyjen toteutussuunnitelma 15.11.2026"

<!-- END .temp-kansio: hallinnoi open-desk-infra/workstations/WSL2/playbooks/05-repo-temp-symlinks.yml -->

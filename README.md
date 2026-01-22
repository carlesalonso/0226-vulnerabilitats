# 0226. RA3: Anàlisi vulnerabilitats

En aquesta activitat analitzarem les vulnerabitilitats d'un sistema informàtic mitjançant una eina d'escaneig de vulnerabilitats. L'objectiu és identificar possibles punts febles en la seguretat del sistema i proposar mesures per a mitigar-los.

## Entorn de treball

Usarem una màquina virtual OpenVAS com eina d'anàlisi. Aquesta màquina la teniu disponible en forma .ova a la unitat de xarxa. [OpenVAS](https://www.openvas.org) és un producte de codi obert que permet realitzar escanejats de vulnerabilitats en sistemes informàtics. Malgrat això, hi ha diversos nivells de llicència, en funció de les funcionalitats que es vulguin utilitzar.

Com a màquina objectiu, usarem una màquina virtual Linux amb diverses vulnerabilitats conegudes. Aquesta màquina també la teniu disponible en forma .ova a la unitat de xarxa. És la coneguda com a [metasploitable-2](https://sourceforge.net/projects/metasploitable/files/Metasploitable2/). Si la baixeu d'Internet, descarregareu un .zip que conté únicament l'arxiu de disc, però no la màquina virtual completa.

## Preparació de l'entorn

### Equip a escannejar

1. Descarregeu la .OVA corresponent a metasplotible-linux al vostre equip.
2. Importeu la màquina virtual a VirtualBox, **assegureu-vos que la ruta on importarà la màquina és la que voleu utilitzar**.
3. Configureu la màquina per tal que utilitzi xarxa en mode "xarxa-NAT".
4. Inicieu la màquina, les credencials per defecte són:
   - Usuari: `msfadmin`
   - Contrasenya: `msfadmin`
5. Un cop iniciada la màquina, obriu una terminal i executeu la comanda `ip a` per obtenir la IP assignada a la màquina. Anoteu aquesta IP, ja que la necessitareu més endavant.

### Equip amb OpenVAS

1. Descarregeu la .OVA corresponent a OpenVAS al vostre equip.
2. Importeu la màquina virtual a VirtualBox, **assegureu-vos de nou, que la ruta on importarà la màquina és la que voleu utilitzar**.
3. Configureu la màquina per tal que utilitzi dues interfícies de xarxa, la primera en mode "xarxa-NAT" per tal tenir connectivitat a Internet i amb la màquina objectiu, i la segona en mode "host-only" per tal de poder accedir a la interfície web des del vostre equip.
4. Inicieu la màquina, les credencials per defecte són:
    - Usuari: `admin`
    - Contrasenya: `admin`
5. Un cop iniciada la màquina, s'obrirà un menú d'inicialització. En aquest menú, per exemple, us demanen la llicència, que podeu obviar 'Skip'. El que sí que caldrà fer són dues accions importants:
    - Definir l'usuari que usarem per entrar via web, per comoditat triarem un usuari `admin` amb contrasenya `admin`.
    - Configurar la xarxa de les dues interfícies, aquí cal seleccionar en cadascuna d'elles l'opció dhcp de IPv4. Finalment, anoteu les dues adreces.

En aquest vídeo teniu un exemple de com fer aquesta configuració inicial:


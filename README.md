# MainWeb

### StartUp
Potřebujete ještě JSON soubory, z které se čerpají data. Já používám Linux takže jsou na absolutní cestě /opt/Projekt/.. .
Stačí jen přepsat cestu v souboru ***MainWeb\Components\Pages\UtokPage.razor*** a vlastnosti SelectedDocker
- v tomto souboru je podstatě veškerá moje práce, chtěl jsem udělat web co nejdynamičtější a aby kažý uživatel měl svůj docker na kterým se může učit.

##### Jak by to mělo fungovat
1. Učitel z jiného rozhraní spustí několik různých předpřipravených dockerů a nadiktuje IP adresy studentům
2. Každý student si vybere svou IP adresu -> naskenované docker kontejnery jsou v proměnné ***runningDockerContainers***
3. Ze souborů se innerjoinem zvolí správný útok a nahraje se do statické třídy ***MainClass*** a z té se následně čerpají veškerá data k uživateli

> 2 soubory jsou proto že z jednoho si bere data i učitelské rozhraní

### Problém
Zkoušel jsem si zapnout několik dockerů a vybrat si jeden pomocí IP adresy. Ten se bezproblémů nahrál a viděl jsem přesně to co jsem chtěl. Funkcionalita byla taky skvělá (jako nápovědy nebo submit otázky `Entrem`). Pak jsem šel zpět na výběr dockerů pomocí IP a když jsem si vybral jakýkoliv jiný tak to spadlo a pomohl jen restart Webu
- mám pocit že to je problém někde v session mezi klientem a serverem.. jakoby zůstávali někde viset data :D, ale to je asi jen můj pocit
- Kontroloval jsem MainClass když jsem si chtěl znovu vybrat docker a zjistil jsem že z inner-joinu nedostanu žádné data i když před tím jsem je dostal

> Všechno se to děje ve vlastnosti SelectedDocker.. to mi spustí event z nabindovaného HTML selectu

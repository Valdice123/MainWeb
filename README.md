# MainWeb
web pro studenty k dockeru

### StartUp
Potřebujete ještě JSON soubory, z které se čerpají data. Já používám Linux takže jsou na absolutní cestě /opt/Projekt/.. .
Stačí jen přepsat cestu v souboru MainWeb\Components\Pages\UtokPage.razor
- v tomto souboru je podstatě veškerá moje práce, chtěl jsem udělat web co nejdynamičtější a aby kažý uživatel měl svůj docker na kterým se může učit.

##### Jak by to mělo fungovat
1. Učitel z jiného rozhraní spustí několik různých předpřipravených dockerů a nadiktuje IP adresy studentům
2. Každý student si vybere svou IP adresu -> naskenované docker kontejnery jsou inicializované v proměnné ***runningDockerContainers***
3. Ze souborů se innerjoinem zvolí správný útok a nahraje se do

### Problém
Zkoušel jsem si zapnout několik dockerů a vybrat si 

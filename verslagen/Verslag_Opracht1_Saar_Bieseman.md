# VERSLAG: Opdracht 1 - Package Manager - Markdown

> SAAR BIESEMAN

## Beschrijving

In deze opdracht leerden we een package manager kennen. Hiermee centraliseer je de installatie en het onderhoud van software.

Er werd verwacht dat wij met een package manager konden werken. Door een script te schrijven in een terminal en daardoor het proces te automatiseren. Je bespaar heel veel tijd met dit te gebruiken.


## Antwoorden op de vragen in de opdracht
### Vraag 1
- De PowerShell-prompt toont de map waar we ons nu bevinden. Wat is de naam van deze directory?
   * Current Working Directory = C:\Windows\system32
### Vraag 2
- In welke map heb je het script bewaard?
   * C:\Users\saarb\Desktop\TI-1G\semester 2\System Engineering Lab\1-package-manager-markdown
### Vraag 3
- In welke map is het script bewaard in de screenshot onder stap 3?
   * D:\Users\BertVV\Documents\HoGent\SELab


- Verander de kleur van de uitvoer: ` Write-Host "text" -BackgroundColor black -ForegroundColor green`


#### WinGet
**Taak**                                                                | **Commando** |
| ----------------------------------------------------------------------- | ------------ |
| Een lijst tonen van de software die nu geïnstalleerd is via apt         | `winget list`|
| Alle packages die nu geïnstalleerd zijn bijwerken tot de laatste versie |`winget upgrade --all`|
| Via de console een package opzoeken                                     | `wignet search <naam package>`             |
| Een geïnstalleerde applicatie verwijderen                               | `winget uninstall <pakketid>`             |

### Vraag 4
De opties `-e en --id` doen voor `winget install`:

  - **`-e`**: (of `-exact`) dwingt WinGet een exacte match te zoeken voor de te installeren applicatie.

  - **`--id`**: hiertegen zeggen dat de tekst die gevolg wordt door deze optie het id is van een applicatie en niet de algemene naam van de software.



`winget pin` zorgt ervoor dat winget bij een volgende update geen nieuwe minor versie, van de applicatie die je wilt updaten, installeert.

## Evaluatiecriteria
- [x] Je hebt een package manager voor jouw besturingssysteem geïnstalleerd.
- [x] Je hebt een script (PowerShell of Bash, afhankelijk van je besturingssysteem) geschreven en gebruikt om de opgesomde applicaties te installeren.
- [ ] Je toont inzicht in de werking van een package manager en kan deze vlot kan gebruiken om basistaken uit te voeren.
- [x] Er is een verslag gemaakt op basis van het template.
- [ ] Elk teamlid heeft de eigen cheat sheet aangevuld met nuttige commando's uit deze opdracht.
- [ ] Je hebt GitHub correct geconfigureerd op je toestel en je hebt de basiscommando's (via CLI) in je vingers.
- [x] Er is een correct antwoord gegeven op de vragen die zijn aangeduid met een :question:.

## Problemen en oplossingen

Beschrijf hieronder eventuele problemen die jullie zijn tegengekomen tijdens het uitvoeren van de opdracht, met een korte beschrijving van wat er mis ging en hoe jullie het hebben opgelost (als het jullie gelukt is om het op te lossen). Als het niet gelukt is om het op te lossen, beschrijf dan hoe ver jullie zijn gekomen en wat jullie tegenhield om verder te gaan. Voeg eventuele foutmeldingen, screenshots, enz. toe.

Als jullie geen problemen zijn tegengekomen, schrijf dan "geen problemen ondervonden".

### Probleem 1 - Korte beschrijving van het probleem

Beschrijf hier het probleem uitgebreid met screenshots, code snippets, enz. en de oplossing die jullie al dan niet hebben gevonden.

## Voorbereiding demo

Beschrijf hier hoe je elk evaluatiecriterium zal demonstreren. Geef ook aan welke bestanden, commando's, enz. je zal gebruiken tijdens de demo.

## Reflecties

Maak werk van een degelijke reflectie over de opdracht.

Wat was moeilijk? Wat was eenvoudig? Wat hebben jullie geleerd van de opdracht? Wat zouden jullie anders doen als jullie het opnieuw moesten doen?

Als jullie nog andere opmerkingen hebben over de opdracht hebben, voel je vrij om ze te delen.

## Bronnen
GrantMeStrength. (z.d.). Use WinGet to install and manage applications. Microsoft Learn. https://learn.microsoft.com/en-us/windows/package-manager/winget/

GrantMeStrength. (z.d.-a). install Command. Microsoft Learn. https://learn.microsoft.com/en-us/windows/package-manager/winget/install

Sdwheeler. (z.d.). about_Comparison_Operators - PowerShell. Microsoft Learn. https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7.5

```powershell
#Automatiseren software-installatie
Write-Host "Software voor System Engineering Lab"

$keuzeALG = Read-Host "Wilt u de algemene applicaties installeren? (y/n)"
if ($keuzeALG -eq "y"){
Write-Host "Installatie algemene applicaties" -ForegroundColor red
    winget install -e --id Git.Git
    winget install -e --id Adobe.Acrobat.Reader
    winget install -e --id Mozilla.Firefox
    winget install -e --id GitHub.GitHubDesktop
    winget install -e --id Microsoft.VisualStudioCode 
    winget install -e --id VideoLAN.VLC
    winget install -e --id 7zip.7zip
}

$keuzeSDP = Read-Host "Wilt u de software voor SDP installeren? (y/n)"
if ($keuzeSDP -eq "y"){
Write-Host "Installatie voor SDP" -ForegroundColor red
    winget install -e --id Oracle.MySQL
    winget install -e --id JetBrains.IntelliJIDEA
    winget install -e --id VisualParadigm.VisualParadigm
}

$keuzeSEL = Read-Host "Installeer software voor SEL? (y/n)"
if ($keuzeSEL -eq "y") {
    Write-Host "Installatie voor SEL" -ForegroundColor red
    winget install -e --id Oracle.VirtualBox
}

$keuzePERS = Read-Host "Installeer persoonlijke applicaties? (y/n)"
if ($keuzePERS -eq "y") {
    Write-Host "Installatie voor persoonlijke applicaties" -ForegroundColor red
    winget install -e --id Spotify.Spotify
    winget install -e --id Discord.Discord
}

Write-Host "Alle installaties zijn uitgevoerd!" -ForegroundColor green
```




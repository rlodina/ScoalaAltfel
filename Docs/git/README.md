##GIT
aplicație software care are grija de surse (Source Code Management , Version Control System) - vezi pe net.

![GIT_CONCEPT](Git.png)

Te poți gândi ca la un dropbox cu facilitați sublime de versionare și istoric al modificărilor pentru fiecare fișier. 

##GitHub - adevăratul facebook al programatorilor. 
- aplicație web/serviciu care oferă serviciu de GIT

### Fă-ți un cont pe github (http://github.com)
 (încercă să-ți alegi un nume de user cât de cât onorabil - este cam aiurea la 35 de ani sa ai un cont de genul: bogdanelCelTareSiMare)

####A. Crează un repository

![Git create repo](Git-CreateRepo.png)

După creare te duce în pagina repo-ului. Deocamdată ai aici un singur fișier: README.md.
Fișierele cu extensia md (markdown) sunt fișiere text care conțin și câteva convenții legate de formatare - detalii pe net. 

####B. Instalează GitHub desktop
Aplicație client (o instalez pe calculatorul meu) care-mi permite să "sincronizez" un repo (structura de directoare și conținutul acestora) cu portalul GitHub.

Download de la adresa https://desktop.github.com/ o aplicație care o instalezi la tine pe sistem. Pasul final este să-ți introduci contul și parola de pe GitHub.

####C. Clonare repo creat la punctul A la tine pe sistem
Pornește aplicața instalată la punctul B.

![GIT_CONCEPT](Git-clone1.png)

La selecția butonului "Clone **ScoalaAltfel**" trebuie să selectez un director de pe HDD-ul meu unde va clona (copia) repo-ul:


![GIT_CONCEPT](Git-clone2.png)

La apăsarea butonului OK - tot ce am în repo-ul ScoalaAltfel de pe GitHub este copiat la mine pe sistem. In cazul meu: C:\Work\ScoalaAltfel

De acum înainte orice fișier pe care-l creez în acest director în care am clonat repo-ul (C:\Work\ScoalaAltfel) îl pot sincroniza cu GitHub-ul.

Pt. test eu am creat un director nou : ProiectA și în el un fișier README.md

####D. Commit - Sincronizarea directorului (repo-ului) local cu cel de pe GitHub:

Pornesc aplicația GitHub (instalata la pasul B):

![GIT commit](Git-commit.png)

Această aplicație o vom folosi și la școală și acasă astfel încât vom lucra mereu pe aceleași surse.

Când pleci de la școală să nu uiți să dai logout:
 - dreapta sus icon: _Tools and option_
 - din meniu selectezi: _Options_
 - în pagina Options este butonul de _LogOut_
 

####Comenzi Git
În mod normal toate aceste comenzi se dau din linia de comandă (da din prompterul DOS):

1. _git add ._ - adaugă toate fisierele (.) în zona pregătitoare pentru commit
2. _git commit 


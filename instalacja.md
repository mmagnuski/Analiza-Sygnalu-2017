# Instalacja

Podstawowe pakiety jakie będą Wam potrzebne podczas warsztatów to:
* Anaconda - dystrybucja pythona i wielu pakietów do analizy i wizualizacji danych (korzystamy z pythona 3.5, ale jeżeli ktoś woli 2.7 - nie powinno być problemu)
* `seaborn` - do ładnych wizualizacji
* `mne` (inaczej mne-python) - pakiet do analizy danych elektrofizjologicznych
* `mypy` - mój pakiet, który będzie Wam potrzebny do różnych dodatkowych operacji - np. będzie ułatwiał niektóre operacje na danych eeg. Do ściągnięcia tego pakietu bezpośrednio z GitHub'a będziecie potrzebowali oprogramowania `git`, które jest dostępne z konsoli `cmder`, którą zainstalujecie.
  
:exclamation: Jako, że instalacja nie jest trywialna i możecie mieć z nią problemy - otworzyłem na naszej platformie [specjalny wątek](https://github.com/mmagnuski/EEG01/issues/2), w ramach którego będę pomagał Wam przezwyciężyć trudności instalacyjne. Jeżeli coś Wam nie działa - śmiało piszcie!

## Anaconda
Python oraz jego standardowa biblioteka, którą mamy na starcie (np. moduł `os` czy `glob`), oferują podstawową funkcjonalność. Do analizy danych potrzebujemy przeróżnych dodatkowych pakietów. Polecana dystrybucja pythona, z której będziemy korzystać na warsztatach to [Anaconda](https://www.continuum.io/downloads). Anaconda zawiera wiele standardowych pakietów używanych do analizy i wizualizacji danych takich jak `numpy`, `matplotlib`, `scipy`, `pandas` czy `statsmodels`. Ściągamy instalator dla **pythona 3.6**.  
:warning: Na zdjęciu poniżej zaznaczony jest guzik do ściągnięcia anacondy z pythonem 3.5 (to starszy screenshot - faktycznie ściągacie anacondę z pythonem 3.6) dla 64-bitowego windowsa, jeżeli Twój system jest 32-bitowy, wybierz instalator 32-bitowy. Jeżeli nie wiesz jaki masz system [możesz to sprawdzić stosując się do tych instrukcji](http://windows.microsoft.com/pl-pl/windows/32-bit-and-64-bit-windows).:  
<img src="/img/anaconda_install_00.PNG" width="450">  

Otwieramy instalator, wybieramy instalację dla użytkownika ("only me" - nie wymaga uprawnień administratora)  
<img src="/img/anaconda_install_01.PNG" width="300">  

upewniamy się że oba checkboxy są zaznaczone:  
<img src="/img/anaconda_install_02.PNG" width="300">  

czekamy...  
<img src="/img/anaconda_install_03.PNG" width="300">  

czekamy...  
<img src="/img/anaconda_install_04.PNG" width="300">  

kończymy instalację.  
<img src="/img/anaconda_install_05.PNG" width="300">  

### sprawdzamy czy wszystko działa
Otwieramy konsolę:  
<img src="/img/anaconda_install_06.PNG" width="250">  

uruchamiamy pythona wpisując `python`:  
<img src="/img/anaconda_install_07.PNG" width="500">  

powinno wyświetlić się coś takiego:  
<img src="/img/anaconda_install_08.PNG" width="500">  

Teraz jesteśmy w pythonie - aby z niego wyjść (z powrotem do normalnej konsoli) wpisujemy `quit()`. Można też po prostu zamknąć okienko.

## pakiety niedostępne w ramach Anacondy: `seaborn`
Czasem jednak potrzebujemy innych pakietów, nie dystrybuowanych w ramach Anacondy. Anaconda daje nam na szczęście doskonałe narzędzie do instalowania pakietów (ale też tworzenia wirtualnych środowisk) - `conda`. Gdy chcemy zainstalować pakiet `seaborn` (a chcemy), piszemy w konsoli po prostu:  
```
conda install seaborn
```

później odpowiadamy na zapytanie (patrz screen poniżej): `y`
<img src="/img/anaconda_install_09.PNG" width="500">  


## cmder / git
Aby zainstalować deweloperską werjsę `mne` oraz `mypy` (mój pakiet z którego będziemy korzystać podczas zajęć) bezpośrednio z GitHub'a trzeba wcześniej zainstalować `git` - system kontroli wersji na którym opiera się GitHub. Użytkownicy Maca i Linuxa prawdopodobnie mają już git'a zainstalowanego, mogą oni to sprawdzić wpisując w konsoli:
```
git status
```
Jeżeli wyskoczył Wam taki błąd to znaczy, że macie git'a i możecie pominąć jego instalację:
```
fatal: Not a git repository (or any of the parent directories): .git
```

Użytkownicy Windowsa prawie na pewno git'a nie mają ale zainstalują go sobie wraz z przyjemniejszą od Windowsowego `wiersza poleceń` konsolą - `cmder`:

### `cmder`
Zainstaluj [cmder](http://cmder.net/) i nie wracaj już do mrocznych tuneli `wiersza polecenia` - git'a dostaniesz w prezencie! Po wejściu na [stronę cmder](http://cmder.net/) wybierz pełną instalację:  
<img src="/img/cmder_install_01.PNG" width="500">  
Rozpocznie to ściąganie pliku zip - po jego ściągnięciu rozpakuj go sobie do jakiegoś folderu na komputerze. Możesz na przykład utworzyć sobie folder `cmder` w `C:\Program Files` i tam wypakować pliki. Na koniec dla wygody - utwórz sobie skrót do `Cmder.exe` na pulpicie. `cmder` otwierać będziemy właśnie poprzez ten skrót.

### własnoręczna instalacja git'a
Jeżeli z jakichś powodów nie możesz/ nie chesz korzystać z `git'a` przez `cmder` albo jesteś na Macu/Linuxie i nie masz git'a będziesz musiał(a) ściągnąć go własnoręcznie. Gita znajdziemy wpisując w google `git`:  
<img src="/img/git_install_01.PNG" width="500">  

pierwszy wynik w screenshocie powyżej (https://git-scm.com) to interesująca nas strona, wchodzimy. Na dole po prawej stronie mamy guzik do instalacji gita, kilkamy.  
<img src="/img/git_install_02.PNG" width="500">  

Instalator gita zostanie pobrany automatycznie, wystarczy teraz go odpalić.  
<img src="/img/git_install_03.PNG" width="300">  

następnie przechodzimy całą instalację krok po kroku (nie musicie zmieniać domyślnych ustawień). Upewnijcie się jednak gdy dotrzecie do momentu wyświetlonego poniżej że zaznaczony jest środkowy checkbox. Bez zaznaczenia tej opcji komenda `git` nie będzie działać w konsoli Windowsa i stoswne komendy do instalacji `mypy` mogą nie działać.
<img src="/img/git_install_04.PNG" width="500">  


## `mne`
Niektóre pakiety nie są jednak dostępne w ramach condy. Instalujemy je wtedy za pomocą komendy `pip` (od `python install package`). `pip` to moduł do pythona, który jest dostępny w ramach Anacondy. Działa bardzo podobnie do komendy `conda`, piszemy `pip install nazwa_pakietu`. `mne` można by więc zainstalować tak (**ale w ten sposób go nie instalujcie!**):
```
pip install mne
```
Normalnie tak właśnie byśmy instalowali ten pakiet, ale będziemy korzystać na zajęciach z funkcji dostępnych na razie tylko w deweloperskiej wersji mne (chociaż stosunkowo niedługo powinny być dostępne w ramach kolejnej wersji mne).
Dlatego też skorzystamy z `cmder` do instalacji (albo konsoli jeżeli nie macie cmder a macie git'a). Najpier wybierzcie sobie jakiś folder, w którym byście chcieli mieć folder z `mne`, powiedzmy, że chcemy mieć ten folder w `C:\Program Files`, piszemy wtedy w `cmder`:
```
cd C:\Program Files
```
aby przejść do tego folderu. Następnie korzystamy z komedy git aby ściągnąć z GitHuba mne:
```
git clone https://github.com/mne-tools/mne-python
```
teraz wchodzimy do ściągniętego folderu:
```
cd mne-python
```
i instalujemy w wersji deweloperskiej (umożliwia później update pakietu przez git'a bez konieczności ponownej instalacji):
```
python setup.py develop
```


## `mypy`
Przyda się Wam również pakiet `mypy` - to taka moja przechowalania kodu, z którego często korzystam. Aby zainstalować `mypy` wykonajcie analogiczne kroki co przy instalacji `mne`, np:
```
cd C:\Program Files
git clone https://github.com/mmagnuski/mypy
cd mypy
python setup.py develop
```


## Czy wszystko działa oraz oddanie pracy domowej
Aby sprawdzić czy wszystko działa, wejdźcie z konsoli do python'a:
```
python
```
a następnie wykonajcie następujące komendy (każda z tych komend może trochę potrwać, bo ładuje wiele pakietów):
```python
from mypy import edu
edu.test_system()
```
Następnie - jeżeli nie było błędów - zrób screenshot ekranu, najlepiej tak aby objmował całą konsolę, przykład poniżej:  
<img src="/img/praca_domowa_przykład.PNG" width="500">  

Screenshot ten zamieść na GitHubie w [tym wątku](https://github.com/mmagnuski/EEG01/issues/1).

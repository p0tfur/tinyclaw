# Tiny Claw (Fixed Fork) 🐜

> [!NOTE]
> **This is a fork of Tiny Claw.** For general information, origin context, and the original project, please visit the official repository: [warengonzaga/tinyclaw](https://github.com/warengonzaga/tinyclaw).

## 🇬🇧 English Version

### 🛠️ Three Major Fixes in this Fork

This version of Tiny Claw has been modified to fix critical bugs present in the original distribution, specifically for self-hosted server deployments.

1. **Our version works in Docker!** 🐳
   The original version had an `INITIALIZATION_ERROR` stemming from the `SecretsManager` module attempting to save encryption keys inside an undefined/inaccessible hidden home folder within the container. We forced it to follow the path defined in the volume's environment variable.
2. **Web Setup enabled by default** 🌐
   We changed the `docker-compose.yml` file so that after spinning up the container, the service automatically exposes the setup wizard interface without needing any interaction through the container's terminal (`setup --web`).
3. **Backup codes window without the idiotic auto-redirect!** 🛑
   In the original version, clicking to generate recovery codes immediately redirected the user forward, not giving adequate time to copy or save them, which led to irreversible access loss in case of an emergency. We added a mandatory manual checkbox confirming the backup keys have been saved before the system allows you to proceed.

### 🚀 How to run in Docker

To run this fixed version, simply clone the repository onto your server (e.g., Dell Wyse) and run the following command:

```bash
docker compose up -d --build --force-recreate
```

*Then access your server's address with port `3000` (or via Tailscale, e.g., `https://veles.tail0bd429.ts.net/setup`), to finish the configuration.*

---

## 🇵🇱 Wersja Polska

### 🛠️ Trzy Główne Poprawki w tym Forku

Ta wersja Tiny Claw została zmodyfikowana, aby naprawić krytyczne błędy występujące w oryginalnej dystrybucji, szczególnie przy wdrożeniach na własnych serwerach.

1. **Nasza wersja działa w Dockerze!** 🐳
   Oryginalna wersja posiadała błąd `INITIALIZATION_ERROR` wynikający z tego, że moduł `SecretsManager` próbował zapisać klucze szyfrujące wewnątrz niezdefiniowanego/niedostępnego ukrytego folderu domowego w kontenerze. Zmusiliśmy go do podążania za ścieżką zdefiniowaną w zmiennej środowiskowej wolumenu.
2. **Setup przez internet domyślnie włączony** 🌐
   Zmieniliśmy plik docker-compose, aby po postawieniu kontenera usługa automatycznie wystawiała interfejs setupu bez interakcji z terminalem kontenera (`setup --web`).
3. **Kody bezpieczeństwa bez idiotycznego auto-redirectu!** 🛑
   W oryginalnej wersji kliknięcie wygenerowania kodów odzyskiwania natychmiastowo przekierowywało użytkownika dalej, nie dając odpowiedniej ilości czasu na ich skopiowanie czy zapisanie, co powodowało utratę dostępu w razie awarii. Dodaliśmy wymóg ręcznego zaznaczenia checkboxa potwierdzającego zapisanie kluczy zapasowych zanim system pozwoli przejść dalej.

### 🚀 Jak uruchomić w Dockerze

Aby uruchomić tę poprawioną wersję po prostu sklonuj repozytorium na swój serwer (np. Dell Wyse) i uruchom komendę:

```bash
docker compose up -d --build --force-recreate
```

*Następnie wejdź na adres swojego serwera z portem `3000` (albo przez Tailscale itp. np. `https://veles.tail0bd429.ts.net/setup`), by dokończyć konfigurację.*

---

## 📃 License
This project is licensed under [GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.html). 
Credits for the original creation go to [Waren Gonzaga](https://github.com/warengonzaga).

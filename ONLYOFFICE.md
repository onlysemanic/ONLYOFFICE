# Installationsguide til ONLYOFFICE

Følg denne guide for at installere ONLYOFFICE i Ubuntu 26.02

---

## 1. Opdatér systemet og pakkelisterne

```bash
sudo apt update && sudo apt upgrade -y
```

---

## 2. Tilføj GPG-nøgle til ONLYOFFICE

```bash
mkdir -p -m 700 ~/.gnupg
curl -fsSL https://download.onlyoffice.com/GPG-KEY-ONLYOFFICE | gpg --no-default-keyring --keyring gnupg-ring:/tmp/onlyoffice.gpg --import
chmod 644 /tmp/onlyoffice.gpg
sudo chown root:root /tmp/onlyoffice.gpg
sudo mv /tmp/onlyoffice.gpg /usr/share/keyrings/onlyoffice.gpg
```

---

## 3. Tilføj softwarelager til ONLYOFFICE

```bash
echo "deb [signed-by=/usr/share/keyrings/onlyoffice.gpg] https://download.onlyoffice.com/repo/debian squeeze main" | sudo tee /etc/apt/sources.list.d/onlyoffice.list
```

---

## 4. Opdatér pakkelisterne

```bash
sudo apt-get update
```

---

## 5. Installér Microsoft standardskrifttyper (msscorefonts)

```bash
sudo apt-get install ttf-mscorefonts-installer
```

---

## 6. Installér ONLYOFFICE Docs

```bash
sudo apt-get install onlyoffice-documentserver
```

---

## 7. Åben ONLYOFFICE

```bash
http://<ip>/
```

---

Du kan nu tilgå ONLYOFFICE i din foretrukne webbrowser.

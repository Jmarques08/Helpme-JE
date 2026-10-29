# Help Me — versão iPhone (.ipa)

Este projeto é a versão iOS do mesmo app do APK: mesmo nome ("Help Me"), mesmo ID
(`app.helpme.cliente`), mesmo ícone, tela de abertura verde e o mesmo site
(`https://vizinho-zezinho1.vercel.app`).

O .ipa é gerado pelo **GitHub**, num Mac na nuvem, de graça. Você não precisa ter Mac.

---

## Parte 1 — Gerar o .ipa no GitHub (≈ 10 min)

1. Crie uma conta em **github.com** (se ainda não tiver).
2. Clique em **New repository** → nome `helpme-ios` → marque **Public**
   (repositório público tem Mac na nuvem ilimitado e grátis) → **Create repository**.
3. Na página do repositório, clique em **uploading an existing file**.
4. Descompacte o `helpme-ios.zip` no computador e **arraste todo o conteúdo da pasta**
   (não a pasta em si) para a página. Clique em **Commit changes**.
5. Confira se a pasta `.github/workflows` subiu (pastas com ponto às vezes ficam
   ocultas). Se não aparecer: **Add file → Create new file**, digite o nome
   `.github/workflows/build-ipa.yml`, cole o conteúdo desse arquivo e salve.
6. Abra a aba **Actions**. O processo "Gerar .ipa (iPhone)" começa sozinho
   (ou clique nele → **Run workflow**). Leva uns 5–10 minutos.
7. Quando ficar verde ✅, clique no processo e, embaixo, em **Artifacts**, baixe
   **HelpMe-ipa**. Dentro do zip está o **HelpMe.ipa**.

## Parte 2 — Instalar no iPhone (com Apple ID grátis)

O .ipa sai **sem assinatura** — o iPhone só aceita depois de assinado. O programa
**Sideloadly** (sideloadly.io, Windows ou Mac) assina com o seu Apple ID e instala:

1. Instale o **Sideloadly** no computador (no Windows, instale também o iTunes e o
   iCloud baixados do site da Apple, não da Microsoft Store).
2. Ligue o iPhone no cabo USB e toque em **Confiar** no iPhone.
3. Abra o Sideloadly, arraste o **HelpMe.ipa**, digite seu **Apple ID** e clique **Start**.
   (Dica: use um Apple ID secundário, se tiver.)
4. No iPhone, ative o **Modo de Desenvolvedor**:
   Ajustes → Privacidade e Segurança → Modo de Desenvolvedor → ligar → reiniciar.
5. Autorize o app: Ajustes → Geral → **VPN e Gerenciamento de Dispositivos** →
   toque no seu Apple ID → **Confiar**.
6. Pronto — o ícone **Help Me** aparece na tela de início.

### Limites da conta grátis
- O app **expira em 7 dias**; para renovar, repita o passo 3 (o Sideloadly pode
  fazer isso automaticamente com o iPhone na mesma rede Wi-Fi).
- No máximo 3 apps instalados assim ao mesmo tempo.
- Só instala em aparelhos ligados ao seu computador.

## Para distribuir para outras pessoas (TestFlight / App Store)

Precisa da conta **Apple Developer** (US$ 99/ano). Com ela, o app pode ser assinado de
verdade e enviado ao TestFlight (link de teste para até 10.000 pessoas) ou à App Store.
Nesse caso, registre o Bundle ID `app.helpme.cliente` na conta e adicione o
certificado e o perfil de distribuição ao workflow.

---

## Para mudar algo

- **Endereço do site**: `capacitor.config.json` → `server.url`.
- **Nome que aparece no iPhone**: `ios/App/App/Info.plist` → `CFBundleDisplayName`.
- **Ícone / tela de abertura**: troque `assets/icon.png` (1024×1024) e `assets/splash.png`
  e rode `npx capacitor-assets generate --ios`.

Cada alteração enviada ao GitHub gera um .ipa novo automaticamente.

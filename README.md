### Languages

<details>
  <summary>English</summary>

# NitenOS

## Introduction

An unattended.xml file to make Windows 11 more efficient and less latency.

## Requirements

- Windows 11  
  - *(Tested on Windows 11 24H2)*
  - *(Only 64-bit supported)*

## What Does NitenOS unattended.xml Do?

The unattended.xml answer file comes with detailed descriptions for nearly all configurations and registry tweaks, which are available for inspection here on GitHub. For customization, download the answer file and open it in editors like [Cursor](https://www.cursor.com/) or [VSCode](https://code.visualstudio.com/).

### Sources and Contributions

<details>
  <summary>Click to Show</summary>

- **Base Answer File Generation**:
  - [Schneegans Unattend Generator](https://schneegans.de/windows/unattend-generator/)

</details>

### Key Features

- Ability to choose Windows Edition (Pro is recommended)
- Bypasses Windows 11 system requirements
- Windows Defender and User Account Control services still working
- Allows execution of PowerShell scripts by default
- Skips forced Microsoft account creation during Windows setup
- Removes preinstalled bloatware apps except daily things like Microsoft Edge, Photos etc.
  - Copilot and Recall is Disabled.
- Sets privacy-related registry keys to disable telemetry
- Disables unnecessary scheduled tasks
- Configures Windows services for optimal performance

> [!NOTE] 
> The features of this xml file are organized for the daily user. After installing Windows with it, you can make changes for better performance, such as turning off Windows Defender or using Ultimate Performance Plan.

## How to Use

To use an answer file, include `autounattend.xml` at your Windows Installation Media to be executed during Windows setup.

> [!IMPORTANT]  
> Ensure the answer file is named `autounattend.xml`; otherwise, it won’t be recognized by the installer.

### Methods
#### Method 1: Create a Bootable Windows Installation USB
<details>
  <summary>Click to Show Instructions</summary>

  1. Download the `autounattend.xml` file and save it on your computer.
  2. Create a [Windows 11](https://www.microsoft.com/en-us/software-download/windows11) Bootable Installation USB drive with [Rufus](https://rufus.ie/en/) or the Media Creation Tool.
  
     > **Important**  
     > - Some users have reported issues with the Media Creation Tool when creating the Windows Installation USB. Use it at your own discretion.  
     > - When using Rufus, don’t select any of the checkboxes in “Customize Your Windows Experience,” as it creates another `autounattend.xml` file that might overwrite settings in the our file.

  3. Copy the `autounattend.xml` file you downloaded in Step 1 to the Bootable Windows Installation USB you created in Step 2.
  4. Boot from the Windows Installation USB, do a clean install of Windows as normal, and the scripts will run automatically.

</details>

#### Method 2: Use Ventoy Auto Install Plugin
<details>
  <summary>Click to Show Instructions</summary>

  1. Download the `autounattend.xml` file and save it on your computer.
  2. Download the [Windows 11](https://www.microsoft.com/en-us/software-download/windows11) ISO file, depending on the version you want.
  3. Download and install [Ventoy](https://github.com/ventoy/Ventoy) to your desired USB flash drive.
  4. Prepare the folder structure:
      - In your newly created Ventoy USB disk, create the following folders: `ISO` and `Templates`. <br/> *They should be at the root of the drive.*
      - Inside of the `ISO` folder, create a new folder called `Windows`.
      - Copy your Windows ISO files in the `ISO\Windows` folder.
      - Copy your `autounattend.xml` into the `Templates` folder.
  5. Start VentoyPlugson. Depending on your OS, the steps might differ.
      - On Windows, run the `VentoyPlugson.exe` file.
      - A new browser window should open up with a Ventoy web interface ready to go.
      - Select the `Auto Install Plugin` menu from the list.
      - Click on the `Add` button.
      - Select [parent] to make the whole Windows ISO folder benefit from the plugin.
      - In the Directory Path, paste in the absolute path to your `Windows` folder. </br> example: `F:\ISO\Windows` (Replace `F` with your drive letter.)
      - In the Template Path, paste in the absolute path to your `autounattend.xml` file. </br> example: `F:\Templates\autounattend.xml` (Replace `F` with your drive letter.) <br/> (PSA: If you have more `autounattend.xml` files, you can add them later on!)
      - Click on `OK` and you should see a message saying that the configuration has been saved successfully.
      - Close the VentoyPlugson browser window and stop the VentoyPlugson application.
  6. Boot from the Ventoy USB drive in the computer where you want to install windows.
     - After selecting a Windows ISO to boot from, you will be prompted to boot with the `/Templates/autounattend.xml` file.
     - Select that option and the `autounattend.xml` will be automatically executed during installation.

</details>

## FAQ

### Why don't I have internet after installing Windows?

<details>
  <summary>Click to Show Instructions</summary>

  If you’re unable to connect to the internet after installation, it’s likely because your Wi-Fi or LAN (Ethernet) drivers are missing. Windows sometimes doesn’t include all necessary drivers for network adapters, especially if they’re specific to your device.

  To resolve this, follow these steps:

  1. **Download your network driver** from the manufacturer’s website on another computer with internet access. Look for Wi-Fi or LAN drivers specific to your device model.
  2. **Transfer the driver** to your Windows installation via USB drive.
  3. **Install the driver** on your Windows system and restart if necessary.

  After installation, you should be able to connect to the internet.

</details>

### Why isn't Microsoft Edge Uninstalled?

<details>
  <summary>Click to Show Explanation</summary>

  Basicly, for daily users who already using Microsoft Edge in life.

</details>

</details>

<details>
  <summary>Türkçe</summary>

# NitenOS

## Giriş

Windows 11'i daha verimli ve düşük gecikmeli hale getirmek için bir unattended.xml dosyası.

## Gereksinimler

- Windows 11  
  - *(Windows 11 24H2 üzerinde test edilmiştir)*
  - *(Sadece 64-bit desteği bulunur)*

## NitenOS unattended.xml Ne Yapar?

Unattended.xml dosyası, neredeyse tüm yapılandırmalar ve kayıt defteri ayarları için ayrıntılı özelleştirmelerle birlikte gelir ve GitHub'da incelenebilir. Özelleştirmek için, xml dosyasını indirip [Cursor](https://www.cursor.com/) veya [VSCode](https://code.visualstudio.com/) gibi editörlerde açabilirsiniz.

### Kaynaklar ve Katkılar

<details>
  <summary>Görmek İçin Tıklayın</summary>

- **Temel xml Dosyasını Oluşturma**:
  - [Schneegans Unattend Generator](https://schneegans.de/windows/unattend-generator/)

</details>

### Temel Özellikler

- Windows Sürümü seçme imkanı (Pro önerilir)
- Windows 11 sistem gereksinimlerini atlar
- Windows Defender ve Kullanıcı Hesabı Denetimi hizmetleri çalışır durumda kalır
- PowerShell komut dosyalarının varsayılan olarak çalıştırılmasına izin verir
- Windows kurulumunda zorunlu Microsoft hesabı oluşturmayı atlar
- Microsoft Edge, Fotoğraflar gibi günlük uygulamalar dışında önceden yüklenmiş gereksiz uygulamaları kaldırır
  - Copilot ve Recall devre dışı bırakılmıştır.
- Telemetriyi devre dışı bırakmak için gizlilikle ilgili kayıt defteri anahtarlarını ayarlar
- Gereksiz, zamanlanmış görevleri devre dışı bırakır
- Windows hizmetlerini kısmen, performans için yapılandırır

> [!NOT] 
> Bu xml dosyasının özellikleri günlük kullanıcı için düzenlenmiştir. Windows'u bununla kurduktan sonra, daha iyi performans için Windows Defender'ı kapatmak veya Nihai Performans güç planını kullanmak gibi değişiklikler yapabilirsiniz.

## Nasıl Kullanılır

xml dosyasını kullanmak için, Windows Kurulum Medyanıza `autounattend.xml` dosyasını ekleyin.

> [!ÖNEMLİ]  
> xml dosyasının `autounattend.xml` olarak adlandırıldığından emin olun; aksi takdirde Windows yükleme tanımayacaktır.

### Yöntemler
#### Yöntem 1: Önyüklenebilir Windows Kurulum USB'si Oluşturma
<details>
  <summary>Talimatları Görmek için Tıklayın</summary>

  1. `autounattend.xml` dosyasını indirin ve bilgisayarınıza kaydedin.
  2. [Rufus](https://rufus.ie/en/) veya Medya Oluşturma Aracı ile [Windows 11](https://www.microsoft.com/en-us/software-download/windows11) Önyüklenebilir USB sürücüsü oluşturun.
  
     > **Önemli**  
     > - Bazı kullanıcılar Windows Kurulum USB'sini oluştururken Medya Oluşturma Aracı ile ilgili sorunlar yaşamıştır. Kendi takdirinize bağlı olarak kullanın.  
     > - Rufus kullanırken, dosyamızdaki ayarların üzerine yazabilecek başka bir `autounattend.xml` dosyası oluşturduğundan, “Windows Deneyiminizi Özelleştirin” bölümündeki onay kutularından hiçbirini seçmeyin.

  3. Adım 1'de indirdiğiniz `autounattend.xml` dosyasını Adım 2'de oluşturduğunuz USB sürücüsüne kopyalayın.
  4. Bilgisayarınızı USB'den boot edin ve temiz bir Windows kurulumu yapın..

</details>

#### Yöntem 2: Ventoy Otomatik Kurulum Eklentisi Kullanma
<details>
  <summary>Talimatları Görmek için Tıklayın</summary>

  1. `autounattend.xml` dosyasını indirin ve bilgisayarınıza kaydedin.
  2. İstediğiniz sürüm bir [Windows 11](https://www.microsoft.com/en-us/software-download/windows11) ISO dosyasını indirin.
  3. [Ventoy](https://github.com/ventoy/Ventoy) programını indirin ve USB sürücünüze kurun.
  4. Klasör mimarisini hazırlayın:
      - Yeni oluşturduğunuz Ventoy USB diskinizde şu klasörleri oluşturun: `ISO` ve `Templates`. <br/> *Bunlar sürücünün kök dizininde olmalıdır.*
      - `ISO` klasörünün içine ismi `Windows` olan yeni bir klasör oluşturun.
      - Windows ISO dosya veya dosyalarınızı `ISO\Windows` klasörüne kopyalayın.
      - Adım 1'de indirdiğiniz `autounattend.xml` dosyasını `Templates` klasörüne kopyalayın.
  5. VentoyPlugson'ı başlatın. İşletim sisteminize bağlı olarak adımlar farklı olabilir.
      - `VentoyPlugson.exe` dosyasını çalıştırın.
      - Kullanıma hazır Ventoy web arayüzü ile yeni bir tarayıcı penceresi açılmalıdır.
      - Listeden `Auto Install Plugin` menüsünü seçin.
      - `Add` butonuna basın.
      - Tüm Windows ISO klasörünün eklentiden yararlanmasını sağlamak için [parent] seçeneğini seçin.
      - `Directory Path` kısmına, `Windows` klasörünüzün yolunu yapıştırın. </br> örnek: `F:\ISO\Windows` (`F` yerine sürücü harfinizi yazın).
      - `Template Path` kısmına, `autounattend.xml` dosyasının yolunu yapıştırın. </br> örnek: `F:\Templates\autounattend.xml` (`F` yerine sürücü harfinizi yazın) <br/> (BilgilendirmeDaha fazla `autounattend.xml` dosyanız varsa, bunları daha sonra ekleyebilirsiniz!)
      - `OK`a tıkladığınızda yapılandırmanın başarıyla kaydedildiğini belirten bir mesaj göreceksiniz.
      - VentoyPlugson tarayıcı penceresini kapatın ve VentoyPlugson uygulamasını durdurun.
  6. Windows'u yüklemek istediğiniz bilgisayarda Ventoy USB sürücüsünden boot edin.
     - Boot için bir Windows ISO'su seçtikten sonra, `/Templates/autounattend.xml` dosyası ile boot seçeneği çıkacaktır.
     - Bu seçeneği seçtiğinizde `autounattend.xml` kurulum sırasında otomatik olarak çalıştırılacaktır.
</details>

## SSS

### Kurulumdan sonra neden internet bağlantım yok?

<details>
  <summary>Talimatları Görmek için Tıklayın</summary>

  Kurulumdan sonra internete bağlanamıyorsanız, bunun nedeni muhtemelen Wi-Fi veya LAN (Ethernet) sürücülerinizin eksik olmasıdır. Windows bazen ağ bağdaştırıcıları için gerekli tüm sürücüleri içermez, özellikle de bunlar cihazınıza özelse.

  Bunu çözmek için aşağıdaki adımları izleyin:

  1. **Ağ sürücünüzü** üreticinin web sitesinden internet erişimi olan başka bir bilgisayara indirin. (Cihaz modelinize özel Wi-Fi veya LAN sürücülerini arayın.)
  2. **Sürücüyü** USB sürücü aracılığıyla Windows kurulumunuza aktarın.
  3. Windows sisteminize veya kurulumada **sürücüyü** yükleyin ve gerekirse yeniden başlatın.

  Kurulumdan sonra internete bağlanabiliyor olmalısınız.
  
</details>

### Microsoft Edge Neden Kaldırılmadı?

<details>
  <summary>Açıklamayı Görmek için Tıklayın</summary>

  Basitçe, hayatında zaten Microsoft Edge kullanan günlük kullanıcılar için.

</details>

</details>

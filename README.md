# No Comments on Media

**Minimal WordPress plugin that automatically disables comments on media attachments.**

[![WordPress Plugin Version](https://img.shields.io/badge/version-1.1.0-blue.svg)](https://github.com/zdrave08/no-comments-on-media)
[![WordPress Compatibility](https://img.shields.io/badge/wordpress-6.0%2B-brightgreen.svg)](https://wordpress.org/)
[![PHP Version](https://img.shields.io/badge/php-8.0%2B-purple.svg)](https://php.net/)
[![License](https://img.shields.io/badge/license-GPLv2-red.svg)](https://www.gnu.org/licenses/gpl-2.0.html)

---

## 📋 Description

**No Comments on Media** is an ultra-lightweight plugin that automatically disables comments on all media attachment pages. No complications, no bloat - just clean, minimal code.

### Why do you need this plugin?

Media attachment pages (images, videos, PDFs) **rarely** need comments. This plugin:

✅ **Improves SEO** - Removes unnecessary comment sections  
✅ **Increases security** - Reduces spam and potential security vulnerabilities  
✅ **Cleans your site** - More professional appearance of attachment pages  
✅ **Saves resources** - Fewer database queries, faster loading  

---

## ✨ Features

### 🎯 Core Features

- **Automatic comment disabling** - Comments can no longer be added to attachments
- **Disables trackbacks/pingbacks** - Complete spam protection
- **Removes Comments section** - Completely hides comment form and existing comments
- **Theme-agnostic** - Works with **any** WordPress theme
- **Simple ON/OFF toggle** - Easy control in Settings → Media
- **Auto-close on activation** - Closes comments on all existing attachments upon activation

### 🎁 Bonus Features

- **Optional comment deletion** - Toggle to permanently delete existing comments on attachments
- **WP-CLI support** - Professional commands for developers and system admins
- **Status monitoring** - Display current state of comments on media

---

## 🚀 Installation

### Automatic installation (WordPress.org)

1. Go to **Plugins → Add New**
2. Search for **"No Comments on Media"**
3. Click **"Install Now"** and then **"Activate"**
4. Done! Plugin works automatically

### Manual installation

1. Download plugin files
2. Upload folder to `/wp-content/plugins/`
3. Activate plugin through **Plugins** menu
4. Plugin starts working automatically

---

## 📖 Usage

Plugin works automatically after activation. To control functionality:

### Admin Panel

1. Go to **Settings → Media**
2. Find **"Comments on Media"** section
3. Configure options:
   - ☑ **Disable comments on all media attachments** - Main functionality
   - ☑ **Delete existing comments on attachments** - ⚠️ Permanently deletes comments (optional)
4. Save changes

**Plugin is enabled by default.**

### WP-CLI Commands

For developers and system administrators:

```bash
# Check status
wp media-comments status

# Disable comments
wp media-comments disable

# Enable comments
wp media-comments enable

# Delete all comments on media (with confirmation)
wp media-comments cleanup

# Delete without confirmation
wp media-comments cleanup --yes
```

**Usage example:**

```bash
$ wp media-comments status

=== No Comments on Media - Status ===

Plugin Status: ENABLED
Attachments with open comments: 0
Total comments on attachments: 45

Success: Comments are disabled on media attachments.
```

---

## 🔧 Technical Details

### WordPress Hooks

Plugin uses the following hooks:

- `comments_open` - Disables ability to open comments
- `pings_open` - Disables pingbacks/trackbacks
- `comments_array` - Returns empty comment array for attachments
- `init` - Removes comment support from attachment post type
- `template_redirect` - Replaces comments template with blank file
- `admin_init` - Registers settings

### What happens on activation?

1. Sets default option to `enabled`
2. Closes comments on **all existing** attachments
3. Plugin starts working immediately

### Comment Deletion

Plugin **DOES NOT DELETE** existing comments by default. It only hides them. 

**If you want to permanently delete comments:**

1. **Via Admin:** Settings → Media → check "Delete existing comments on attachments"
2. **Via WP-CLI:** `wp media-comments cleanup --yes`

⚠️ **Note:** This action is **permanent** and cannot be undone. We recommend backing up before deletion.

---

## 📦 File Structure

```
no-comments-on-media/
├── no-comments-on-media.php  # Main plugin file (~400 lines)
├── blank.php                  # Blank template for comments
├── readme.txt                 # WordPress.org readme
└── README.md                  # This documentation
```

---

## 🎨 Performance & SEO

- ⚡ **Ultra fast** - Minimal overhead, only necessary hooks
- 🪶 **Extremely lightweight** - ~400 lines of code
- 🔍 **SEO friendly** - Removes unnecessary sections, faster loading
- 🎯 **Zero bloat** - No unnecessary features
- 🌐 **Theme-agnostic** - Works with any theme

---

## 📋 Requirements

- **WordPress:** 6.0 or newer (tested up to 7.1)
- **PHP:** 8.0 or newer
- **MySQL:** 5.6 or newer (WordPress standard)

---

## ❓ FAQ

### Does the plugin delete existing comments?

**By default NO.** Plugin only hides comments. However, there is an option for permanent deletion:
- Admin: Settings → Media → "Delete existing comments on attachments"
- CLI: `wp media-comments cleanup`

### Does it disable trackbacks/pingbacks too?

**Yes!** Plugin disables both comments and trackbacks/pingbacks on all media attachments.

### Does it work with my theme?

**Yes!** Plugin is theme-agnostic and works with all WordPress themes (custom themes, page builders, block themes).

### Does it affect comments on posts/pages?

**No.** Plugin affects **only** media attachments. Comments on posts and pages are not affected.

### Does it slow down the site?

**No.** Plugin is ultra-lightweight and uses minimal resources. No negative impact on performance.

### Compatibility with caching plugins?

**Yes.** Compatible with all caching plugins (WP Super Cache, W3 Total Cache, WP Rocket, etc.).

### Can I use the plugin via command line?

**Yes!** Plugin has full WP-CLI support with commands: `disable`, `enable`, `cleanup`, `status`.

### Is it safe to delete comments?

Deletion is **permanent** and cannot be undone. **Make a backup** before using this option. Use only if you're sure you don't need the comments.

---

## 📄 License

GPL v2 or later - [https://www.gnu.org/licenses/gpl-2.0.html](https://www.gnu.org/licenses/gpl-2.0.html)

---

## 👨‍💻 Author

**Zdravko Lukic**  
GitHub: [@zdrave08](https://github.com/zdrave08)

---

## 🐛 Support

For help:

- **GitHub Issues:** [github.com/zdrave08/no-comments-on-media/issues](https://github.com/zdrave08/no-comments-on-media/issues)
- **WordPress.org Support:** [wordpress.org/support/plugin/no-comments-on-media/](https://wordpress.org/support/plugin/no-comments-on-media/)

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first.

### Development

```bash
# Clone repository
git clone https://github.com/zdrave08/no-comments-on-media.git

# Install in WordPress
cp -r NoCommentsOnMedia /path/to/wordpress/wp-content/plugins/
```

---

## 📝 Changelog

### 1.1.0 - 2026-11-19
- Requires PHP 8.0+ and WordPress 6.0+
- Tested up to WordPress 7.1
- LICENSE file is now GPLv2, matching the plugin header

### 1.0.0 - 2025-11-18
- 🎉 Initial release
- ✅ Disable comments and pingbacks/trackbacks on media attachments
- ✅ Remove comment forms and sections
- ✅ Simple ON/OFF toggle
- ✅ Optional: Delete existing comments
- ✅ WP-CLI support (disable, enable, cleanup, status)
- ✅ Auto-close existing comments on activation

---

**Made with ❤️ for the WordPress community**

---

# No Comments on Media (Serbian)

[![WordPress Plugin Version](https://img.shields.io/badge/version-1.1.0-blue.svg)](https://github.com/zdrave08/no-comments-on-media)
[![WordPress Compatibility](https://img.shields.io/badge/wordpress-6.0%2B-brightgreen.svg)](https://wordpress.org/)
[![PHP Version](https://img.shields.io/badge/php-8.0%2B-purple.svg)](https://php.net/)
[![License](https://img.shields.io/badge/license-GPLv2-red.svg)](https://www.gnu.org/licenses/gpl-2.0.html)

---

## 📋 Opis

**No Comments on Media** je ultra-lagani plugin koji automatski isključuje komentare na svim media attachment stranicama. Bez komplikacija, bez bloat-a - samo čist, minimalan kod.

### Zašto vam je potreban ovaj plugin?

Media attachment stranice (slike, videi, PDF-ovi) **retko** trebaju komentare. Ovaj plugin:

✅ **Poboljšava SEO** - Uklanja nepotrebne comment sekcije  
✅ **Povećava sigurnost** - Smanjuje spam i potencijalne bezbednosne propuste  
✅ **Čisti vaš sajt** - Profesionalniji izgled attachment stranica  
✅ **Štedi resurse** - Manje database queries, brže učitavanje  

---

## ✨ Funkcionalnosti

### 🎯 Core Features

- **Automatsko isključivanje komentara** - Komentari se više ne mogu dodavati na attachments
- **Isključuje trackbacks/pingbacks** - Potpuna zaštita od spam-a
- **Uklanja Comments sekciju** - Potpuno sakriva comment form i postojeće komentare
- **Theme-agnostic** - Radi sa **bilo kojom** WordPress temom
- **Simple ON/OFF toggle** - Jednostavna kontrola u Settings → Media
- **Auto-close na aktivaciji** - Pri aktivaciji zatvara komentare na svim postojećim attachmentima

### 🎁 Bonus Features

- **Opciono brisanje komentara** - Toggle za trajno brisanje postojećih komentara na attachments
- **WP-CLI podrška** - Profesionalne komande za developere i system admine
- **Status monitoring** - Prikaz trenutnog stanja komentara na media

---

## 🚀 Instalacija

### Automatska instalacija (WordPress.org)

1. Idite na **Plugins → Add New**
2. Pretražite **"No Comments on Media"**
3. Kliknite **"Install Now"** i zatim **"Activate"**
4. Gotovo! Plugin radi automatski

### Ručna instalacija

1. Preuzmite plugin fajlove
2. Otpremite folder u `/wp-content/plugins/`
3. Aktivirajte plugin kroz **Plugins** meni
4. Plugin automatski počinje da radi

---

## 📖 Korišćenje

Plugin radi automatski nakon aktivacije. Za kontrolu funkcionalnosti:

### Admin Panel

1. Idite na **Settings → Media**
2. Pronaćite sekciju **"Comments on Media"**
3. Konfigurisanje opcija:
   - ☑ **Disable comments on all media attachments** - Glavna funkcionalnost
   - ☑ **Delete existing comments on attachments** - ⚠️ Trajno briše komentare (opciono)
4. Sačuvajte promene

**Plugin je omogućen po defaultu.**

### WP-CLI Komande

Za developere i system administratore:

```bash
# Provera statusa
wp media-comments status

# Isključivanje komentara
wp media-comments disable

# Uključivanje komentara
wp media-comments enable

# Brisanje svih komentara na media (sa potvrdom)
wp media-comments cleanup

# Brisanje bez potvrde
wp media-comments cleanup --yes
```

**Primer korišćenja:**

```bash
$ wp media-comments status

=== No Comments on Media - Status ===

Plugin Status: ENABLED
Attachments with open comments: 0
Total comments on attachments: 45

Success: Comments are disabled on media attachments.
```

---

## 🔧 Tehnički detalji

### WordPress Hooks

Plugin koristi sledeće hookove:

- `comments_open` - Isključuje mogućnost otvaranja komentara
- `pings_open` - Isključuje pingbacks/trackbacks
- `comments_array` - Vraća prazan array komentara za attachments
- `init` - Uklanja comment support sa attachment post type-a
- `template_redirect` - Zamenjuje comments template sa praznim fajlom
- `admin_init` - Registruje settings

### Šta se dešava pri aktivaciji?

1. Postavlja default opciju na `enabled`
2. Zatvara komentare na **svim postojećim** attachmentima
3. Plugin odmah počinje da radi

### Brisanje komentara

Plugin **NE BRIŠE** postojeće komentare po defaultu. Samo ih sakriva. 

**Ako želite da trajno obrišete komentare:**

1. **Via Admin:** Settings → Media → čekirajte "Delete existing comments on attachments"
2. **Via WP-CLI:** `wp media-comments cleanup --yes`

⚠️ **Napomena:** Ova akcija je **trajna** i ne može se opozvati. Preporučujemo backup pre brisanja.

---

## 📦 Struktura fajlova

```
no-comments-on-media/
├── no-comments-on-media.php  # Glavni plugin fajl (~160 linija)
├── blank.php                  # Prazan template za comments
├── readme.txt                 # WordPress.org readme
└── README.md                  # Ova dokumentacija
```

---

## 🎨 Performance & SEO

- ⚡ **Ultra brz** - Minimalni overhead, samo neophodni hookovi
- 🪶 **Extremely lightweight** - ~160 linija koda
- 🔍 **SEO friendly** - Uklanja nepotrebne sekcije, brže učitavanje
- 🎯 **Zero bloat** - Nema nepotrebnih features
- 🌐 **Theme-agnostic** - Radi sa bilo kojom temom

---

## 📋 Zahtevi

- **WordPress:** 6.0 ili noviji (testirano do 7.1)
- **PHP:** 8.0 ili noviji
- **MySQL:** 5.6 ili noviji (standard za WordPress)

---

## ❓ FAQ

### Da li plugin briše postojeće komentare?

**Po defaultu NE.** Plugin samo sakriva komentare. Međutim, postoji opcija za trajno brisanje:
- Admin: Settings → Media → "Delete existing comments on attachments"
- CLI: `wp media-comments cleanup`

### Da li isključuje i trackbacks/pingbacks?

**Da!** Plugin isključuje i komentare i trackbacks/pingbacks na svim media attachmentima.

### Radi li sa mojom temom?

**Da!** Plugin je theme-agnostic i radi sa svim WordPress temama (custom themes, page builders, block themes).

### Da li utiče na komentare na posts/pages?

**Ne.** Plugin utiče **samo** na media attachments. Komentari na postovima i stranicama nisu zahvaćeni.

### Da li usporava sajt?

**Ne.** Plugin je ultra-lagani i koristi minimalne resurse. Nema negativnog uticaja na performanse.

### Kompatibilnost sa caching pluginima?

**Da.** Kompatibilan sa svim caching pluginima (WP Super Cache, W3 Total Cache, WP Rocket, itd).

### Mogu li koristiti plugin preko command line?

**Da!** Plugin ima punu WP-CLI podršku sa komandama: `disable`, `enable`, `cleanup`, `status`.

### Je li bezbedno brisati komentare?

Brisanje je **trajno** i ne može se opozvati. **Napravite backup** pre korišćenja ove opcije. Koristite samo ako ste sigurni da vam komentari ne trebaju.

---

## 📄 Licenca

GPL v2 ili novija - [https://www.gnu.org/licenses/gpl-2.0.html](https://www.gnu.org/licenses/gpl-2.0.html)

---

## 👨‍💻 Autor

**Zdravko Lukic**  
GitHub: [@zdrave08](https://github.com/zdrave08)

---

## 🐛 Podrška

Za pomoć:

- **GitHub Issues:** [github.com/zdrave08/no-comments-on-media/issues](https://github.com/zdrave08/no-comments-on-media/issues)
- **WordPress.org Support:** [wordpress.org/support/plugin/no-comments-on-media/](https://wordpress.org/support/plugin/no-comments-on-media/)

---

## 🤝 Doprinos

Pull requests su dobrodošli! Za veće izmene, molimo prvo otvorite issue.

### Development

```bash
# Clone repository
git clone https://github.com/zdrave08/no-comments-on-media.git

# Install u WordPress
cp -r NoCommentsOnMedia /path/to/wordpress/wp-content/plugins/
```

---

## 📝 Changelog

### 1.1.0 - 2026-11-19
- Zahteva PHP 8.0+ i WordPress 6.0+
- Testirano do WordPress 7.1
- LICENSE fajl je sada GPLv2, u skladu sa zaglavljem plugina

### 1.0.0 - 2025-11-18
- 🎉 Initial release
- ✅ Disable comments and pingbacks/trackbacks on media attachments
- ✅ Remove comment forms and sections
- ✅ Simple ON/OFF toggle
- ✅ Optional: Delete existing comments
- ✅ WP-CLI support (disable, enable, cleanup, status)
- ✅ Auto-close existing comments on activation

---

**Napravljen sa ❤️ za WordPress zajednicu**


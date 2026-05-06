<h1 align="center">
  <img src="https://raw.githubusercontent.com/Clorabase/Clorabase/main/clorabase-banner.png" alt="Clorabase" width="800">
</h1>

<h3 align="center">
  🚀 Turn Your GitHub Repo Into a NoSQL Database
</h3>

<p align="center">
  <strong>A free, serverless Backend-as-a-Service for Android & Java applications</strong>
</p>

<p align="center">
  <a href="https://github.com/Clorabase/Clorabase">
    <img src="https://img.shields.io/badge/Version-0.6-green?style=for-the-badge" alt="Version">
  </a>
  <a href="https://github.com/Clorabase/Clorabase/stargazers">
    <img src="https://img.shields.io/github/stars/Clorabase/Clorabase?style=for-the-badge" alt="Stars">
  </a>
  <a href="https://github.com/Clorabase/Clorabase/issues">
    <img src="https://img.shields.io/github/issues/Clorabase/Clorabase?color=red&style=for-the-badge" alt="Issues">
  </a>
  <a href="https://github.com/Clorabase/Clorabase/network/members">
    <img src="https://img.shields.io/github/forks/Clorabase/Clorabase?color=teal&style=for-the-badge" alt="Forks">
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Author-ErrorxCode-cyan?style=flat-square" alt="Author">
  <img src="https://img.shields.io/badge/Open%20Source-Yes-green?style=flat-square" alt="Open Source">
  <img src="https://img.shields.io/badge/Made%20In-Kotlin%20%26%20Java-orange?style=flat-square" alt="Made In">
</p>

---

## 💡 About Clorabase

**Clorabase** is a lightweight, serverless **Backend-as-a-Service (BaaS)** designed specifically for Android and Java applications. It leverages **GitHub** as both a storage and database provider, enabling developers to build apps without managing complex backend infrastructure.

Perfect for **small apps, hobby projects, and non-commercial use cases** where cost efficiency and simplicity matter most.

---

## ✨ Key Features

### 🗄️ **Clorastore Database**
A NoSQL-like database storing data as encrypted JSON files in a GitHub repository.
- Nested collections support
- Document-based CRUD operations
- Basic querying capabilities

### 📦 **Integrated Storage**
Two modes of file management:
- Standard uploads (< 50 MB) directly to the repository
- Large file uploads via GitHub Release assets

### 💬 **In-App Messaging (Android)**
Remote messaging service for showing custom dialogs:
- Coupon notifications
- Promotional messages
- Simple custom dialogs

### 🔄 **In-App Updates (Android)**
Version management utility for apps outside the Play Store:
- Flexible or immediate update prompts
- Controlled via `version.json`

### 🔐 **Security**
- All records encrypted with **AES** before pushing to GitHub
- Your data stays in your GitHub repository

### 💰 **Zero Cost**
- Fully free and open-source
- Powered by GitHub's infrastructure
- No subscription or hidden fees

---

## 📊 Tech Stack

<div align="center">

| Language | Usage |
|----------|-------|
| **Kotlin** | 44.3% |
| **Java** | 37.9% |
| **HTML** | 17.8% |

</div>

---

## 🚀 Quick Start

### Installation

Add JitPack repository to your **build.gradle**:

```gradle
allprojects {
    repositories {
        maven { url 'https://jitpack.io' }
    }
}
```

Add dependency in module **build.gradle**:

**For Android:**
```gradle
implementation 'com.github.Clorabase.Clorabase:Clorabase4A:0.6'
```

**For Java:**
```gradle
implementation 'com.github.Clorabase.Clorabase:Clorabase4j:0.6'
```

### Initialize Clorabase

```java
try {
    Clorabase clorabase = Clorabase.getInstance("username", "token", "project");
} catch (Exception e) {
    e.printStackTrace();
}
```

### Basic Usage

**Database Operations:**
```java
ClorastoreCollection db = clorabase.getDatabase();
Map<String, Object> data = new HashMap<>();
data.put("name", "Rahil");
data.put("role", "Admin");

db.collection("users").document("user1")
  .setData(data)
  .addOnSuccessListener(v -> Log.d("DB", "Data saved!"));
```

**Storage Operations:**
```java
ClorabaseStorage storage = clorabase.getStorage();
ClorabaseStorage imagesDir = storage.directory("images");

imagesDir.uploadFile(inputStream, "avatar.png", new ProgressListener() {
    @Override
    public void onProgress(long bytesRead, long totalBytes) {
        // Track progress
    }
    @Override
    public void onComplete() {
        Log.d("Storage", "Upload complete!");
    }
});
```

📚 **For detailed documentation, visit:** [Clorabase Wiki](https://mintlify.wiki/Clorabase/Clorabase/)

---

## 🔑 Generate GitHub Token

Clorabase requires a **GitHub Personal Access Token (PAT)**:

1. Go to **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (classic)**
2. Click **Generate new token**
3. Select the `repo` scope (full control of private repositories)
4. Copy and store the token securely

⚠️ **Important:** Never commit your token to public repositories. GitHub will automatically revoke exposed tokens.

---

## 📈 Clorabase vs Firebase

| Feature | Clorabase | Firebase |
|---------|-----------|----------|
| **Cost** | 💰 100% Free | 💵 Tiered / Pay-as-you-go |
| **Use Case** | Small apps, hobby projects | Enterprise, scalable apps |
| **Data Ownership** | Your GitHub repo | Google Servers |
| **Setup** | Very Easy | Moderate to Complex |
| **Database** | NoSQL | NoSQL |
| **In-App Messaging** | ✅ Supported | ✅ Supported |
| **In-App Updates** | ✅ Supported | ❌ Not Available |
| **Authentication** | ❌ Not Available | ✅ Built-in |
| **Scalability** | Small to Medium | Enterprise Scale |

### ✅ Choose Clorabase When:
- Your priority is **staying within budget** (completely free)
- Building **personal or hobby projects**
- App is **Android/Java only**
- You need a **simple data model**
- You prefer a **DIY approach**

---

## 🤝 Contributing

We welcome contributions! Whether it's bug reports, feature requests, or code improvements:

- 🐛 **Report Bugs** → [GitHub Issues](https://github.com/Clorabase/Clorabase/issues)
- 💡 **Suggest Features** → [GitHub Discussions](https://github.com/Clorabase/Clorabase/discussions)
- 📝 **Contribution Guide** → See [contribution.md](https://github.com/Clorabase/Clorabase/blob/main/contribution.md)

---

## 📞 Support & Contact

**Creator:** Rahil Khan ([@ErrorxCode](https://github.com/ErrorxCode))

For personal assistance:
- 📧 Email: x0.khanrahil@gmail.com
- 📱 Instagram: [@x1.rahil](https://instagram.com/x1.rahil)

---

## ⭐ Show Your Support

If Clorabase helped you build something awesome, please:
- ⭐ **Star this repository**
- 👀 **Watch for updates**
- 🔄 **Share with your friends**

Your support motivates us to keep improving Clorabase!

---

<div align="center">

**Made with ❤️ by the Clorabase community**

[![Readme Quotes](https://quotes-github-readme.vercel.app/api?type=horizontal&theme=dracula)](https://github.com/piyushsuthar/github-readme-quotes)

</div>

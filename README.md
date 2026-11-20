# 引っ越し飛脚 (Hikkoshi Hikyaku) 〜Blog Migration Converter〜

A lightweight, privacy-first web application that converts **WordPress XML (WXR)** export files (including **Ameba Ownd**) into **Google Blogger Atom XML** format.

🔗 **Live Demo:** [https://tortoisebleu.github.io/wordpress-to-blogger/](https://tortoisebleu.github.io/wordpress-to-blogger/)

---

## ✨ Key Features

* **100% Client-Side & Privacy-First:** All XML parsing and conversions happen locally in your browser. Your blog data is never uploaded to any external server.
* **Batch File Merging:** Drag and drop multiple WordPress/Ameba Ownd XML files at once to merge them seamlessly into a single Blogger-compatible XML file without duplicate post ID conflicts.
* **Bulk Image Backup (ZIP):** Automatically extracts all image URLs from your posts and downloads them into a single organized `.zip` archive (`YYYY-MM-DD_0001.jpg`, etc.) to prevent data loss when migrating from closing platforms.
* **Image URL List Export:** Export extracted image URLs as a detailed `.csv` (with post dates and titles) or a plain `.txt` list for external download managers.
* **Formatting Options:** Toggle draft inclusion and automatic `<br>` line-break conversion before exporting.

---

## 🚀 How to Use

1. Open the **[Live Demo](https://tortoisebleu.github.io/wordpress-to-blogger/)**.
2. Drag and drop one or more exported `.xml` files into the drop zone.
3. Click **"Blogger用XMLをダウンロード"** to download the converted file for Blogger.
4. *(Recommended)* Click **"画像をZIPで一括保存"** to back up all images referenced in your posts locally.
5. In your **Google Blogger Dashboard**, go to **Settings → Manage blog → Import content**, and upload the generated XML file.

---

## 🛠️ Built With

* HTML5 / Vanilla JavaScript (DOMParser, Blob, FileReader)
* [Tailwind CSS](https://tailwindcss.com/) (via CDN)
* [JSZip](https://stuk.github.io/jszip/) (for client-side image archiving)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

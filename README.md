# 🎨 Figma Design Gallery

Automated design project management system that syncs Figma exports with Notion database.

## 📁 Repository Structure

```
figma-design-gallery/
├── illustrations/
│   └── [project-name]/
│       ├── design.fig
│       └── thumbnail.jpg
├── logos/
│   └── [project-name]/
│       ├── design.fig
│       └── thumbnail.jpg
├── ui-designs/
│   └── [project-name]/
│       ├── design.fig
│       └── thumbnail.jpg
├── web-designs/
│   └── [project-name]/
│       ├── design.fig
│       └── thumbnail.jpg
├── mobile-apps/
│   └── [project-name]/
│       ├── design.fig
│       └── thumbnail.jpg
└── processed/
    └── [completed projects moved here]
```

## 🚀 How It Works

1. **Upload**: Add new design projects to category folders
2. **Automation**: Background task scans every 2 hours
3. **Notion**: Creates database entries automatically
4. **Processing**: Moves completed projects to processed folder
5. **Notifications**: Telegram alerts for new projects

## 🔗 Connected Systems

- **Notion Database**: [Design Gallery](https://www.notion.so/Design-Gallery-257e17161f2c81cfbe15c60cbe31eafb)
- **Automation**: Runs every 2 hours via Bhindi Background Tasks
- **Notifications**: Telegram alerts for new projects

## 📋 Project Requirements

Each project folder must contain:
- `design.fig` - Figma source file
- `thumbnail.jpg` - Preview image

## 🎯 Notion Database Fields

- **Project Name**: Extracted from folder name
- **Category**: Auto-detected from folder location
- **Thumbnail**: Direct link to thumbnail.jpg
- **Figma File Link**: Direct link to design.fig
- **Date Added**: Timestamp of processing
- **Status**: New → Processed

## 🔄 Automation Status

✅ Repository created
✅ Folder structure ready
✅ Notion database connected
⏳ Background automation pending setup

---

*Powered by Bhindi AI Automation*
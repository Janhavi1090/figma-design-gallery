# 🎨 Design Gallery Automation Script

## Configuration
- **Repository**: Janhavi1090/figma-design-gallery
- **Notion Database**: 257e1716-1f2c-81cf-be15-c60cbe31eafb
- **Schedule**: Every 2 hours
- **Telegram**: Notifications enabled

## Workflow Steps

### 1. Scan Repository Structure
```
GET /repos/Janhavi1090/figma-design-gallery/contents/
- Check: illustrations/, logos/, ui-designs/, web-designs/, mobile-apps/
- Identify new project folders (not in processed/)
- Verify each project has design.fig + thumbnail.jpg
```

### 2. Process New Projects
For each new project found:
- Extract project name from folder path
- Determine category from parent folder
- Get raw file URLs for design.fig and thumbnail.jpg
- Set status as "New"

### 3. Create Notion Entries
```
POST /v1/pages
Parent: 257e1716-1f2c-81cf-be15-c60cbe31eafb
Properties:
- Name: [Project Name]
- Project Name: [Same as Name]
- Category: [Illustrations/Logos/UI Designs/Web Designs/Mobile Apps]
- Thumbnail: [GitHub raw URL]
- Figma File Link: [GitHub raw URL]
- Date Added: [Current timestamp]
- Status: "New"
```

### 4. Move to Processed
```
- Copy project folder to processed/[category]/[project-name]/
- Delete original folder after successful Notion creation
```

### 5. Send Notifications
```
Telegram message:
"🎨 New design project added: [Project Name] ([Category])
Check your Design Gallery: [Notion URL]"
```

## Error Handling
- Skip folders missing required files
- Retry GitHub API calls up to 3 times
- Continue processing other projects if one fails
- Log all errors for debugging

## Expected Output
```
🎨 Design Gallery Sync Report
📊 Projects Found: X
✅ Successfully Added: Y
⚠️ Errors/Skipped: Z
🔗 Notion Gallery: [URL]
📱 Telegram Sent: Y/N
⏰ Next Run: [Timestamp]
```
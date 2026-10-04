# ใช้ Google Stitch ตกแต่งเว็บ

ติดตั้งแล้ว: `@google/stitch` (devDependency) → `npm install`

## เริ่มต้น
1. สร้าง API key ที่ Stitch แล้ว `export STITCH_API_KEY=...` (หรือ `npm run stitch:login`)
2. ตรวจสอบ: `npm run stitch:status`

## Workflow ปรับหน้าเว็บให้สวย
```bash
npm run stitch:capture -- http://localhost:3000/        # → .stitch/captures/*.html
npx stitch upload screen .stitch/captures/index.html --route / --title Home
npx stitch edit screen <screen-id> --project <project-id> --prompt "ดีไซน์ทันสมัย โทนสีอบอุ่น"
npx stitch generate variants --project <id> --screen <id> --prompt "ลองหลายสไตล์" --count 3
npm run stitch:serve -- -p <project-id> --port 3000     # พรีวิว
```

## ใช้ผ่าน Claude Code (MCP)
`.mcp.json` ตั้งค่า server `stitch` แบบ HTTP (`https://stitch.googleapis.com/mcp`) ไว้แล้ว โดยอ่าน key จาก `STITCH_API_KEY`

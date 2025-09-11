# QR Codes for 00-setup Module

## Purpose
QRコードは、スマートフォンを使っている学習者が簡単にリンクにアクセスできるようにするためのものです。特に、URLを手入力するのが苦手な方や、PCとスマートフォンを併用している方に便利です。

## Required QR Codes

### 1. discord-invite.png
- **Target URL**: [Discord server invite link - to be updated with actual invite URL]
- **Size**: 300x300 pixels
- **Error Correction Level**: High (30% - camera reading with phone)
- **Format**: PNG with transparent background
- **Usage**: Discord community participation for smartphone users

**Surrounding Text in Module**:
```
📱 スマートフォンの方はこちら
下のQRコードをカメラで読み取ってください

[QR CODE]

Discord コミュニティに参加
```

### 2. github-repository.png  
- **Target URL**: https://github.com/pinkie-community/terakoya-textbook
- **Size**: 300x300 pixels
- **Error Correction Level**: High (30%)
- **Format**: PNG with transparent background
- **Usage**: Repository access for smartphone users

**Surrounding Text in Module**:
```
📚 最新の教材はこちら
スマートフォンのカメラで読み取ってください

[QR CODE]

AI寺子屋教科書 GitHub
```

### 3. gemini-mobile-direct.png
- **Target URL**: https://gemini.google.com
- **Size**: 200x200 pixels (smaller, for quick access)
- **Error Correction Level**: Medium (15%)
- **Format**: PNG with transparent background
- **Usage**: Direct mobile browser access to Gemini

**Surrounding Text in Module**:
```
🔗 アプリをダウンロードしたくない方
ブラウザでも利用できます

[QR CODE]

モバイルブラウザでGemini
```

## Implementation Instructions

### Creating QR Codes
1. Use a reliable QR code generator that supports high error correction
2. Test with multiple smartphone cameras before deployment
3. Ensure QR codes work with older smartphones (iPhone 6+, Android 6+)
4. Verify QR codes redirect to correct URLs

### File Specifications
- **File naming**: descriptive-purpose.png
- **Image optimization**: Compress for web while maintaining scannability
- **Backup format**: Keep SVG source files for scalability
- **Version control**: Update QR codes if target URLs change

### Testing Checklist
- [ ] Readable with iPhone camera app (iOS 11+)
- [ ] Readable with Android camera app (Android 6+)
- [ ] Readable with common QR scanner apps
- [ ] Works in various lighting conditions
- [ ] Maintains quality at different screen sizes

## Design Guidelines

### Visual Consistency
- Use consistent sizing within modules
- Maintain adequate white space around QR codes
- Consider adding subtle branding (AI寺子屋 logo in corner)
- Ensure contrast with page background

### User Experience
- Position QR codes near relevant instructions
- Include text alternatives for users who can't scan
- Provide context about what the QR code leads to
- Consider print-friendly versions

### Accessibility
- Always include text description of QR code destination
- Provide alternative access methods (typed URLs)
- Consider users with visual impairments
- Test with various screen reader software

## Maintenance Schedule

### Regular Updates
- Check QR code functionality monthly
- Update if target URLs change
- Regenerate if visual quality degrades
- Test with new smartphone models

### Content Alignment
- Ensure QR codes match current module content
- Update instructions if scanning behavior changes
- Coordinate with Discord server administrators
- Verify GitHub repository links remain accurate

## Integration with Module Content

### Placement Strategy
QR codes should appear at natural decision points:
1. **Community joining**: After successful Gemini setup
2. **Resource access**: For additional materials
3. **Mobile alternatives**: When desktop instructions are complex

### Instructional Text
Always accompany QR codes with:
- Clear purpose statement
- Step-by-step scanning instructions
- Alternative access method
- Expected outcome description

### Fallback Options
For users who cannot scan QR codes:
- Shortened URLs (bit.ly or similar)
- Step-by-step navigation instructions
- Desktop access alternatives
- Help contact information

## Example Integration

```markdown
### ステップ4: コミュニティに参加（5分）

#### パソコンの方
1. [GitHub: AI寺子屋教科書](https://github.com/pinkie-community/terakoya-textbook) を開く
2. 「Discord コミュニティ」のリンクをクリック
3. 「サーバーに参加」をクリック

#### スマートフォンの方
下のQRコードをスマートフォンのカメラで読み取ってください：

![Discord コミュニティ参加](static/qr-codes/discord-invite.png)

**QRコードが読み取れない場合**:
1. カメラアプリを開く
2. QRコードにカメラを向ける
3. 画面に表示される通知をタップ

**それでもうまくいかない場合**:
- GitHub のページから手動でリンクを探す
- Discord公式サイトで「AI寺子屋」を検索
- コミュニティサポートに連絡
```

## Security Considerations

### URL Validation
- Verify all target URLs are legitimate and safe
- Use HTTPS links where available
- Avoid URL shorteners that could be compromised
- Regular security scans of target destinations

### Privacy Protection
- Ensure QR codes don't encode personal information
- Use public, safe landing pages
- Consider analytics implications of QR code usage
- Provide clear privacy information for community participation
```markdown
# ??? Restaurant Booking App

A modern, interactive restaurant booking application with Google Sheets integration. Perfect for restaurants wanting to accept online reservations and pre-orders.

## ?? Features

- **Table Reservations**: Date, time, and guest count selection
- **Pre-order System**: Interactive menu with real-time pricing
- **Google Sheets Integration**: Automatic data storage
- **Responsive Design**: Works on all devices
- **Modern UI**: Beautiful animations and user experience

## ??? Setup Instructions

### For Restaurant Owners

1. **Fork this repository**
2. **Customize the app:**
   - Update restaurant name in `index.html`
   - Modify menu items and prices
   - Change colors and styling to match your brand
3. **Set up Google Sheets integration** (see below)
4. **Enable GitHub Pages** to publish your app

### Google Sheets Integration

1. **Create a Google Sheet** with these columns:
   ```
   Reservation ID | Customer Name | Phone | Email | Guests | Date | Time | Notes | Order Items | Total | Timestamp
   ```

2. **Create Google Apps Script:**
   - Go to [script.google.com](https://script.google.com)
   - Create new project
   - Paste this code:

   ```javascript
   function doPost(e) {
     const sheet = SpreadsheetApp.openById('YOUR_SHEET_ID').getActiveSheet();
     const data = JSON.parse(e.postData.contents);
     
     sheet.appendRow([
       data.reservationId,
       data.customerName,
       data.phone,
       data.email,
       data.guests,
       data.date,
       data.time,
       data.notes,
       data.orderItems,
       data.total,
       data.timestamp
     ]);
     
     return ContentService.createTextOutput(JSON.stringify({success: true}));
   }
   ```

3. **Deploy the script:**
   - Click "Deploy" > "New Deployment"
   - Type: Web app
   - Execute as: Me
   - Access: Anyone
   - Copy the deployment URL

4. **Update the app:**
   - Replace `YOUR_DEPLOYMENT_ID` in `index.html` with your actual deployment URL
   - Uncomment the fetch code in the JavaScript section

## ?? Customization

### Changing Restaurant Details
- Update the restaurant name and description in the header
- Modify the phone number and contact information

### Menu Customization
- Add/remove menu items in the HTML
- Update prices and descriptions
- Add new categories (beverages, etc.)

### Styling
- Colors: Modify the CSS gradient variables
- Fonts: Update the font-family in CSS
- Layout: Adjust grid layouts and spacing

## ?? Technical Details

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Backend**: Google Apps Script
- **Database**: Google Sheets
- **Hosting**: GitHub Pages
- **Responsive**: Mobile-first design
- **Performance**: Optimized for fast loading

## ?? Analytics Integration

Add Google Analytics by inserting this code before `</head>`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## ?? Deployment

### GitHub Pages
1. Go to repository Settings
2. Scroll to "Pages" section
3. Select "Deploy from a branch"
4. Choose "main" branch
5. Your app will be available at: `https://YOUR_USERNAME.github.io/restaurant-booking-app`

### Custom Domain (Optional)
1. Add a `CNAME` file with your domain name
2. Configure DNS settings with your domain provider
3. Enable HTTPS in GitHub Pages settings

## ?? Mobile App Version

This web app is Progressive Web App (PWA) ready. Users can install it on their phones for a native app experience.

## ?? Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## ?? License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ?? Support

- ?? Email: your-email@example.com
- ?? Issues: [GitHub Issues](https://github.com/YOUR_USERNAME/restaurant-booking-app/issues)
- ?? Discussions: [GitHub Discussions](https://github.com/YOUR_USERNAME/restaurant-booking-app/discussions)

## ?? Acknowledgments

- Built with modern web technologies
- Inspired by the need for simple, effective restaurant booking solutions
- Thanks to the open-source community

---

**Made with ?? for restaurant owners everywhere**
```

### ?? .gitignore
Create a `.gitignore` file:

```
# OS generated files
.DS_Store
.DS_Store?
._*
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db

# IDE files
.vscode/
.idea/
*.swp
*.swo

# Logs
logs
*.log

# Dependency directories
node_modules/

# Optional: Environment files
.env
.env.local
.env.development.local
.env.test.local
.env.production.local
```

### ?? LICENSE
Create a `LICENSE` file:

```
MIT License

Copyright (c) 2025 [Your Name]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## Step 4: Commit and Push Files

```bash
# Add all files
git add .

# Commit with a message
git commit -m "Initial commit: Restaurant booking app with Google Sheets integration"

# Push to GitHub
git push origin main
```

## Step 5: Enable GitHub Pages

1. **Go to your repository** on GitHub
2. **Click "Settings"** tab
3. **Scroll down to "Pages"** section
4. **Under "Source"**, select "Deploy from a branch"
5. **Choose "main"** branch and "/ (root)" folder
6. **Click "Save"**

Your app will be live at: `https://YOUR_USERNAME.github.io/restaurant-booking-app`

## Step 6: Customize for Your Restaurant

1. **Edit index.html:**
   - Change "Bella Vista Restaurant" to your restaurant name
   - Update menu items and prices
   - Modify colors and styling

2. **Update README.md:**
   - Replace YOUR_USERNAME with your GitHub username
   - Add your contact information
   - Update the description

## ?? Optional Enhancements

### Add Google Analytics
```html
<!-- Add before </head> in index.html -->
<script async src="https://www.googletagmanager.com/gtag/js?id=YOUR_GA_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'YOUR_GA_ID');
</script>
```

### Custom Domain
1. Create a `CNAME` file in your repository with your domain
2. Configure DNS with your domain provider
3. Enable HTTPS in GitHub Pages settings

## ?? Troubleshooting

**Common Issues:**
- **Pages not loading**: Check that index.html is in the root directory
- **Styling broken**: Ensure CSS is properly embedded in the HTML
- **Forms not submitting**: Update the Google Apps Script URL

**Getting Help:**
- GitHub Issues: Report bugs or request features
- GitHub Discussions: Ask questions or share ideas
- Stack Overflow: Technical questions

Your restaurant booking app is now published and ready to use! ??

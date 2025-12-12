# Hugo to Squarespace Migration Guide
## St. Matthew's Anglican Church Website

**Last Updated:** December 12, 2025
**Verified Against:** Current Squarespace pricing, features, and processes

This guide provides step-by-step instructions for migrating the St. Matthew's Anglican Church website from Hugo (static site generator) to Squarespace.

---

## Executive Summary (For Pastor Review)

**Key Decision: Which plan to choose?**

| Plan | Cost | Who Can Update | Best For |
|------|------|----------------|----------|
| **Basic** | $16/month ($192/year) | 2 people max | Small church, tight budget, pastor + 1 helper |
| **Core** | $23/month ($276/year) | Unlimited people | Multiple staff/volunteers, room to grow |

**Cost Difference:** $84/year ($7/month)

**To Decide:** List who needs to update the website. If 2 people or fewer, Basic works. If 3+, choose Core.

**Required:** 14-day free trial (no credit card needed to start)

**Quick Prep (Before Starting):**
1. Optimize large image files (reduce from 400KB to ~50-100KB)
2. Delete unused `horizontal-logo-old.png`
3. Note design preferences: Burgundy/gold colors, serif font, traditional style
4. That's it! Site is already well-structured for migration.

---

## Table of Contents

1. [Pre-Migration Planning](#1-pre-migration-planning)
2. [Content Inventory](#2-content-inventory)
3. [Squarespace Account Setup](#3-squarespace-account-setup)
4. [Template Selection & Design](#4-template-selection--design)
5. [Content Migration](#5-content-migration)
6. [Design Implementation](#6-design-implementation)
7. [SEO & Settings Configuration](#7-seo--settings-configuration)
8. [Domain Migration](#8-domain-migration)
9. [Testing Checklist](#9-testing-checklist)
10. [Launch Checklist](#10-launch-checklist)
11. [Post-Migration Tasks](#11-post-migration-tasks)

---

## 1. Pre-Migration Planning

### Recommended Simplifications (Optional but Helpful)

Before migrating, consider these simplifications to make the transition smoother:

#### 1. Content Simplification (HIGH PRIORITY)

**Issue:** Your current site uses custom HTML `<div>` tags for styled callout boxes:
```html
<div class="worship-callout">
  <div class="worship-times">Sundays at 10:00 AM</div>
  ...
</div>
```

**Squarespace Reality:** Squarespace uses a block-based editor. Custom HTML won't automatically style.

**Recommendation:**
- **Don't change anything now** - Keep your Hugo site as-is
- **During migration:** You'll recreate these using Squarespace's built-in blocks:
  - Worship callout → Use "Quote" or "Promotional" block with burgundy background
  - Special notice → Use "Announcement Bar" or "Newsletter" block
  - This is actually easier in Squarespace (drag & drop vs. writing HTML)

#### 2. Social Media Icons (MEDIUM PRIORITY)

**Issue:** Current site uses embedded SVG code for Facebook/YouTube icons (76 lines of code)

**Squarespace Reality:** Has built-in social media icon blocks

**Recommendation:**
- **Don't change anything now**
- **During migration:** Use Squarespace's Social Links block (Settings → Social Links)
- Much simpler and looks professional

#### 3. Image Optimization (MEDIUM PRIORITY - Do This Now)

**Issue:** Some logo files are quite large:
- `adgl-logo.png` - 400 KB
- `acna-logo.png` - 360 KB
- `logo.png` - 172 KB
- `horizontal-logo-old.png` - 68 KB (unused duplicate)

**Recommendation - Do before migration:**
1. Delete unused file: `horizontal-logo-old.png`
2. Optimize large logos using [TinyPNG](https://tinypng.com) or similar:
   - Target: Under 100 KB each for footer logos
   - Target: Under 50 KB for main logo
3. This will make Squarespace site load faster

**Commands to optimize (optional):**
```bash
# Delete old unused logo
rm static/images/horizontal-logo-old.png

# Then upload large PNGs to tinypng.com and replace
```

#### 4. Google Maps Embed (LOW PRIORITY)

**Current:** Using iframe embed code
**Squarespace:** Has built-in Map block

**Recommendation:**
- **Don't change anything**
- **During migration:** Use Squarespace's Map block (just enter address)
- Easier to manage and update

#### 5. Custom CSS (NO ACTION NEEDED)

**Issue:** Current site has 1,068 lines of custom CSS

**Squarespace Reality:** Templates handle most styling

**Recommendation:**
- **Don't port the CSS** - It won't work the same way
- **Instead:** Document your design preferences:
  - Colors: Burgundy #800020, Gold #CFB53B
  - Font: Georgia or similar serif
  - Style: Clean, traditional, elegant
- Choose a Squarespace template that matches these preferences
- Use Squarespace's style editor to set colors and fonts
- Only add minimal custom CSS if absolutely needed for special formatting

#### 6. Content Structure (ALREADY GOOD ✅)

**Current state:** 3 simple pages (Home, About, Contact)

**Squarespace Reality:** Works perfectly

**Recommendation:** No changes needed - this is an ideal structure

---

### Summary: What to Do Now vs. During Migration

**Before Migration (Do Now):**
- ✅ Optimize/compress large image files
- ✅ Delete `horizontal-logo-old.png` (unused)
- ✅ Document design preferences (colors, fonts, style)
- ✅ Create simple text versions of content (strip HTML if desired, but not required)

**During Migration (Handle in Squarespace):**
- Recreate callout boxes using Squarespace blocks
- Add social media using built-in Social Links
- Use Map block instead of iframe
- Set colors/fonts in template style editor

**Don't Bother With:**
- Porting custom CSS (won't work the same)
- Converting HTML to markdown (Squarespace uses blocks anyway)
- Worrying about custom div classes (Squarespace doesn't use them)

**Bottom Line:** Your site is already quite simple and well-structured. The main prep work is image optimization and documenting your design preferences. Everything else can be handled naturally during the Squarespace migration using their block-based editor.

---

### Budget Planning

#### DECISION POINT: Which Squarespace Plan? (Pastor to decide)

**Option 1: Basic Plan - $16/month ($192/year)**
- ✅ Lower cost: Saves $84/year compared to Core
- ✅ **2 contributors maximum** (e.g., Pastor + 1 staff member or volunteer)
- ✅ All essential features for a simple church website
- ✅ Includes domain, hosting, SSL, contact forms
- ❌ No custom code or advanced integrations
- ❌ Cannot add more than 2 people with website access

**Option 2: Core Plan - $23/month ($276/year)**
- ✅ **Unlimited contributors** (Pastor, staff, volunteers can all help)
- ✅ Premium integrations and custom code access if needed
- ✅ No e-commerce transaction fees
- ✅ More professional features
- ❌ Costs $84/year more than Basic

**How to Decide:**

| Choose BASIC if... | Choose CORE if... |
|-------------------|------------------|
| Only 1-2 people will ever update the site | You want 3+ people to have access |
| Pastor handles all updates, maybe 1 assistant | Want flexibility for multiple staff/volunteers |
| Budget is very tight ($84/year matters) | Want room to grow the team |
| Simple site with no special integrations needed | May want advanced features later |

**Questions to Ask:**
1. Who will update the website? (List names)
   - If 2 people or fewer → Basic might work
   - If 3+ people → Need Core
2. Might you want to add contributors in the future?
   - If yes → Core gives flexibility
   - If no → Basic saves money
3. Is $84/year a significant amount in your church budget?
   - If yes → Basic is adequate for a small church
   - If no → Core provides more options

**Additional Costs (Both Plans):**
- **Domain**: Included with annual plan or starts at $14/year
- **Professional Email**: $6/month per mailbox (Google Workspace Business Starter)
  - First year FREE with eligible new subscriptions
  - Business Standard: $12/month, Business Plus: $18/month
  - *Note: Can continue using free Gmail (StMatthewsACT@gmail.com) instead*

**Note:** Squarespace rebranded plans in 2025; plans are now Basic, Core, Plus, Advanced (replaced Personal, Business, Commerce tiers)

### Pre-Migration Checklist

**Simplification Tasks (Do Now):**
- [ ] Optimize image files using [TinyPNG.com](https://tinypng.com):
  - [ ] `adgl-logo.png` (currently 400 KB → target 100 KB)
  - [ ] `acna-logo.png` (currently 360 KB → target 100 KB)
  - [ ] `logo.png` (currently 172 KB → target 50 KB)
- [ ] Delete unused file: `static/images/horizontal-logo-old.png`
- [ ] Document design preferences:
  - [ ] Primary color: Burgundy #800020
  - [ ] Secondary color: Gold #CFB53B
  - [ ] Font preference: Georgia or similar serif
  - [ ] Style: Clean, traditional, elegant

**Key Decisions:**
- [ ] **Which Squarespace plan to use** (see decision table above)
  - [ ] List everyone who needs website update access: _______________
  - [ ] Decision: Basic ($16/month) or Core ($23/month)? _______________
- [ ] Timeline for migration
- [ ] Who will manage the migration
- [ ] Whether to hire a Squarespace designer/developer
- [ ] Data backup strategy for current site

---

## 2. Content Inventory

### Current Site Structure

#### Pages (3 total)
1. **Homepage** (`content/_index.md`)
   - Welcome message and mission statement
   - Worship service times and location
   - Christmas Eve service notice
   - First-time visitor information
   - Google Maps embed
   - Contact information
   - Social media links
   - Pastor information
   - Anglican tradition information

2. **About Page** (`content/about.md`)
   - Mission statement
   - Anglican tradition explanation
   - Worship description
   - Community information
   - Pastor bio

3. **Contact Page** (`content/contact.md`)
   - Church address and meeting location
   - Phone and email
   - Pastor information
   - Social media links

#### Static Assets

**Images** (located in `static/images/`):
- `horizontal-logo.png` - Main church logo (70 KB)
- `acna-logo.png` - Anglican Church in North America logo (367 KB)
- `adgl-logo.png` - Anglican Diocese of the Great Lakes logo (408 KB)
- Favicon files (favicon-16x16.png, favicon-32x32.png)

**Other Assets**:
- `favicon.ico` (191 KB)
- `site.webmanifest`
- CSS stylesheet (`static/css/style.css`)

#### External Integrations
- Google Maps embed
- Facebook page link
- YouTube channel link
- External links to:
  - Anglican Diocese of the Great Lakes (adgl.us)
  - Anglican Church in North America (anglicanchurch.net)
  - Book of Common Prayer 2019 (bcp2019.anglicanchurch.net)

#### Contact Information
- **Phone**: (567) 343-0757
- **Email**: StMatthewsACT@gmail.com
- **Address**: Meeting at Toledo First Seventh-day Adventist Church, 4909 W. Sylvania Ave., Toledo, OH 43623
- **Pastor**: Father Zeke Coughlin
- **Service Times**: Sundays at 10:00 AM
- **Children's Ministry**: Available during 10:00 AM service

#### Key Content Elements to Preserve
- Mission statement: "To Know Christ and To Make Him Known"
- Sunday worship time: Sundays at 10:00 AM
- Meeting location details
- Children's ministry information
- First-time visitor guide
- Anglican tradition explanation
- Pastor information

---

## 3. Squarespace Account Setup

### Step 1: Create Account
1. Go to [squarespace.com](https://www.squarespace.com)
2. Click "Get Started"
3. Use church email: StMatthewsACT@gmail.com
4. Create a strong password (save in secure location)

### Step 2: Start Trial
- Squarespace offers a 14-day free trial
- No credit card required to start
- Full access to all features during trial

### Step 3: Initial Site Setup
1. Choose "Start with a Design" (template selection in next section)
2. Select website type: "Church/Religious Organization"
3. Name your site: "St. Matthew's Anglican Church"

---

## 4. Template Selection & Design

### Recommended Templates for Churches

#### Important Note About Templates:
Squarespace is currently on version 7.1, which offers modern, flexible templates. The templates Bedford, Montauk, Skye, and Five are older Version 7.0 templates that are still available but use older technology.

#### Recommended Approach:
1. **Browse current 7.1 templates** - These are more modern and easier to customize
2. **Look for templates with**:
   - Clean, traditional layouts
   - Good typography for readability
   - Professional appearance suitable for religious organizations
   - Mobile-responsive design (all templates are)

#### If Using Version 7.0 Templates:
1. **Bedford** - Classic, elegant, widely used for businesses and nonprofits
2. **Montauk** - Clean layout, originally for photographers/artists
3. **Skye** - Minimalist, blog-focused with customizable post displays
4. **Five** - Features sidebar capabilities

**Recommendation**: Start with current 7.1 templates for best long-term support and easier customization

### Template Selection Criteria
Your current site has:
- Burgundy (#800020) and gold (#CFB53B) color scheme
- Classic serif typography (Georgia)
- Clean, traditional layout
- Prominent worship callout boxes

**Choose a template that**:
- Supports custom colors (all templates do)
- Has clean typography options
- Allows for prominent call-to-action sections
- Works well with embedded content (Google Maps)
- Is mobile-responsive (all are)

### Design Elements to Consider
- Logo placement (header)
- Navigation menu (Home, About, Contact)
- Footer with contact info and social links
- Embedded maps capability
- Special announcement banners

---

## 5. Content Migration

### Step-by-Step Content Migration

#### Phase 1: Create Page Structure

1. **Create Main Pages**
   - Home (default)
   - About
   - Contact

2. **Set Up Navigation**
   - Configure main navigation: Home → About → Contact
   - Ensure navigation is in header

#### Phase 2: Homepage Migration

**Content Sections to Create:**

1. **Hero/Banner Section**
   - Add church logo image
   - Title: "To Know Christ and To Make Him Known"
   - Can use Squarespace's banner/hero block

2. **Worship Service Times Callout**
   - Use "Quote" or "Promotional" block with burgundy background
   - Content:
     ```
     Sundays at 10:00 AM

     Meeting at Toledo First Seventh-day Adventist Church
     4909 W. Sylvania Ave.
     Toledo, OH 43623

     Children's ministry provided during the 10:00 service,
     with children returning to their families for Holy Communion
     ```

3. **Christmas Eve Service (Special Notice)**
   - Use "Promotional" or "Newsletter" block
   - Add seasonal/special events as needed
   - Content:
     ```
     Christmas Eve Service
     December 24, 6:00 PM
     Toledo First Seventh-day Adventist Church
     4909 W. Sylvania Ave., Toledo, OH 43623
     Join us as we celebrate the birth of our Savior.
     ```

4. **Introduction Text**
   - Use text block
   - Copy from current homepage paragraph starting with "We're a welcoming Christian community..."

5. **First Time Visitors Section**
   - Add heading: "First Time Visitors"
   - Use text block with bullet points
   - Copy all content from current site

6. **Getting Here Section**
   - Add heading: "Getting Here"
   - Add address with link to Google Maps
   - Embed Google Maps:
     - Add "Map" block in Squarespace
     - Enter address: 4909 W. Sylvania Ave., Toledo, OH 43623
     - Or use iframe embed with current map code

7. **Connect With Us**
   - Add phone: (567) 343-0757
   - Add email: StMatthewsACT@gmail.com
   - Add social media icons:
     - Facebook: https://www.facebook.com/people/St-Matthews-Anglican-Church-Toledo/61579296465664/
     - YouTube: https://www.youtube.com/@stmatthewsepiscopalchurcht6968

8. **Our Pastor Section**
   - Heading: "Our Pastor"
   - Text about Father Zeke Coughlin
   - Link to contact page

9. **Anglican Tradition**
   - Brief explanation
   - Links to ADGL and ACNA websites

#### Phase 3: About Page Migration

**Content Sections:**

1. **Page Title**: "About St. Matthew's"

2. **Our Mission**
   - Text block with mission statement
   - Copy from about.md

3. **Our Anglican Tradition**
   - Explanation of Anglican middle way
   - Links to:
     - Anglican Diocese of the Great Lakes: https://www.adgl.us/
     - Anglican Church in North America: https://www.anglicanchurch.net/

4. **Our Worship**
   - Description of liturgy and worship
   - Link to Book of Common Prayer: https://bcp2019.anglicanchurch.net/
   - Bullet list of worship elements

5. **Our Community**
   - Community description
   - Welcoming message

6. **Our Pastor**
   - Father Zeke Coughlin bio
   - Link to contact page

#### Phase 4: Contact Page Migration

**Content Sections:**

1. **Page Title**: "Contact Us"

2. **Introduction**
   - Welcoming message

3. **Church Information**
   - Address (with Google Maps link)
   - Phone number (clickable tel: link)
   - Email address (clickable mailto: link)

4. **Contact Form** (Squarespace Built-in)
   - Add Squarespace form block with fields:
     - Name (required)
     - Email (required)
     - Phone (optional)
     - Message (required)
   - Set form to send to: StMatthewsACT@gmail.com

5. **Our Pastor**
   - Father Zeke info
   - Availability for pastoral care

6. **Social Media**
   - Facebook link
   - YouTube link

#### Phase 5: Asset Migration

**Upload Images:**
1. Go to Design → Custom CSS → Manage Custom Files OR
2. Upload directly when adding image blocks

**Images to Upload:**
- `horizontal-logo.png` (main logo)
- `acna-logo.png` (footer)
- `adgl-logo.png` (footer)
- Favicon (in Site Settings → Browser Icon)

**Favicon Setup:**
1. Settings → Browser Icon
2. Upload favicon.ico or favicon-32x32.png

---

## 6. Design Implementation

### Color Scheme Configuration

1. **Access Design Settings**
   - Go to Design → Site Styles (or Design → Colors depending on template)

2. **Set Primary Colors**
   - Primary/Accent Color: `#800020` (Burgundy)
   - Secondary Color: `#CFB53B` (Gold)
   - Background: `#FEFDF7` (Warm Cream)
   - Text: `#2c2c2c` (Dark Gray)

3. **Additional Colors** (if template supports)
   - Burgundy Light: `#a6002a`
   - Burgundy Dark: `#5a0017`
   - Gold Light: `#d4c159`
   - Antique Gold: `#D4AF37`

### Typography Configuration

1. **Font Families**
   - Headings: Georgia or similar serif (Libre Baskerville, Playfair Display)
   - Body: Georgia or similar serif
   - Note: Squarespace uses Adobe Fonts, so exact match may vary

2. **Font Sizes**
   - Adjust in Design → Site Styles
   - Ensure readability on mobile

### Custom CSS (If Needed)

Access: Design → Custom CSS

**Potential Custom CSS:**

```css
/* Worship Callout Styling */
.sqs-block-quote {
  background: linear-gradient(135deg, #800020 0%, #5a0017 100%);
  color: #FFFFFF;
  padding: 3rem 2rem;
  text-align: center;
  border-top: 3px solid #CFB53B;
}

/* Special Notice Styling */
.special-notice {
  background: #770077;
  color: #FFFFFF;
  padding: 2rem;
  text-align: center;
  border-left: 4px solid #CFB53B;
  border-right: 4px solid #CFB53B;
}

/* Social Media Icons */
.social-icons a {
  color: #800020;
  transition: color 0.3s ease;
}

.social-icons a:hover {
  color: #CFB53B;
}

/* Footer Styling */
footer {
  background: linear-gradient(135deg, #800020 0%, #5a0017 100%);
  color: #FFFFFF;
}
```

### Navigation Setup

1. **Main Navigation**
   - Pages: Home | About | Contact
   - Style: Top navigation bar
   - Configure in: Pages → Main Navigation

2. **Mobile Navigation**
   - Ensure hamburger menu works properly
   - Test on mobile devices

### Footer Configuration

1. **Footer Content**
   - Add footer using template's footer settings
   - Include:
     - Contact information
     - Social media links
     - ADGL and ACNA logos
     - Copyright notice

2. **Footer Blocks** (if supported)
   - Use Squarespace's footer blocks
   - Add text, images, and social icons

---

## 7. SEO & Settings Configuration

### Basic SEO Settings

1. **Site Title & Description**
   - Go to: Settings → Business Information → Site Title
   - Title: `St. Matthew's Anglican Church - Toledo, OH`
   - Description: `Welcome to St. Matthew's Anglican Church in Toledo, Ohio. Join us for worship, fellowship, and community.`

2. **Page SEO Settings**
   For each page (Home, About, Contact):
   - Click page settings (gear icon)
   - SEO tab
   - Set page title, description, and URL slug

**Homepage SEO:**
- Title: `St. Matthew's Anglican Church - Toledo, OH`
- Description: `Join us at St. Matthew's Anglican Church in Toledo. Sundays at 10:00 AM. A welcoming Christian community in the Anglican tradition.`
- URL: `/` (homepage)

**About Page SEO:**
- Title: `About St. Matthew's Anglican Church`
- Description: `Learn about our mission, worship, and Anglican tradition at St. Matthew's in Toledo, Ohio.`
- URL: `/about`

**Contact Page SEO:**
- Title: `Contact St. Matthew's Anglican Church`
- Description: `Get in touch with St. Matthew's Anglican Church in Toledo. Find our location, service times, and contact information.`
- URL: `/contact`

### Google Search Console

1. **Verify Site Ownership**
   - Go to Settings → Advanced → External API Keys
   - Add Google Search Console verification code
   - Or verify via DNS (after domain migration)

2. **Submit Sitemap**
   - Squarespace auto-generates sitemap at: `yourdomain.com/sitemap.xml`
   - Submit to Google Search Console

### Social Media Integration

1. **Social Links**
   - Settings → Business Information → Social Links
   - Add:
     - Facebook: https://www.facebook.com/people/St-Matthews-Anglican-Church-Toledo/61579296465664/
     - YouTube: https://www.youtube.com/@stmatthewsepiscopalchurcht6968

2. **Social Sharing Images**
   - Settings → Business Information → Social Sharing Logo
   - Upload church logo (minimum 200x200px, recommended 1000x1000px)

### Analytics Setup

1. **Google Analytics** (if desired)
   - Settings → Advanced → External API Keys
   - Add Google Analytics tracking code

2. **Squarespace Analytics**
   - Built-in analytics available in Analytics section
   - Track visitors, page views, etc.

### Site Settings

1. **Business Information**
   - Settings → Business Information
   - Fill in:
     - Business Name: St. Matthew's Anglican Church
     - Phone: (567) 343-0757
     - Email: StMatthewsACT@gmail.com
     - Address: 4909 W. Sylvania Ave., Toledo, OH 43623
     - Country: United States

2. **Cookie Banner** (GDPR Compliance)
   - Settings → Cookies & Visitor Data
   - Configure cookie banner if required

3. **Email Settings**
   - Settings → Email
   - Configure contact form notifications
   - Set reply-to email: StMatthewsACT@gmail.com

---

## 8. Domain Migration

### Pre-Migration (While Hugo Site is Still Live)

1. **Document Current DNS Settings**
   - Log into current domain registrar
   - Screenshot/document all DNS records
   - Note nameservers
   - Document email settings (if any)

2. **Lower TTL (Time To Live)**
   - 48 hours before migration, reduce DNS TTL to 300 seconds (5 minutes)
   - This speeds up DNS propagation

### Option A: Transfer Domain to Squarespace

**Pros:**
- Everything in one place
- Included with annual plan
- Easy management

**Cons:**
- Transfer takes 1-15 days (most complete in one week)
- Requires domain to be registered for at least 60 days with current provider
- Domain must be unlocked at current registrar
- Site will be down during transfer unless using Option C below

**Steps:**
1. Settings → Domains → Use a Domain I Own
2. Follow Squarespace's domain transfer process
3. Unlock domain at current registrar
4. Get authorization code
5. Initiate transfer in Squarespace

### Option B: Connect Existing Domain (Point DNS)

**Pros:**
- Faster than transfer (minutes to hours)
- Keep domain at current registrar
- No downtime

**Cons:**
- Domain managed in separate location
- May need to configure separately

**Steps:**

1. **Get Squarespace DNS Information**
   - Settings → Domains → Use a Domain I Own → Connect a Domain You Already Own
   - Squarespace will provide DNS records to add

2. **Update DNS at Current Registrar**
   - Log into your current domain registrar (e.g., Netlify, Namecheap, GoDaddy)
   - Update DNS A records to point to Squarespace:
     - Host: `@` → Squarespace IP addresses (provided by Squarespace)
     - Host: `www` → CNAME to Squarespace (provided by Squarespace)

3. **Wait for DNS Propagation**
   - Can take 24-48 hours
   - Check progress: whatsmydns.net

### Option C: Use Squarespace Temporary URL During Testing

**Best Practice Approach:**

1. **Build site on Squarespace with temporary URL**
   - Use: `yoursite.squarespace.com`
   - Test thoroughly

2. **Once ready to launch, connect domain using Option B**
   - Minimal downtime
   - Switch happens quickly

### Email Considerations

**Current Email Setup:**
- Current email: StMatthewsACT@gmail.com
- This appears to be a Gmail address (not domain-based)

**Options:**
1. **Keep current Gmail** (Recommended for simplicity)
   - No changes needed
   - Continue using StMatthewsACT@gmail.com

2. **Get custom domain email** (e.g., pastor@stmatthewstoledo.org)
   - Squarespace offers Google Workspace: $6/month per mailbox (Business Starter)
   - **FREE for first year** with eligible new subscriptions
   - Settings → Email → Create Email Address
   - More professional appearance
   - Includes 30GB storage, Gmail, Calendar, Meet, Docs, Sheets, Slides

---

## 9. Testing Checklist

### Pre-Launch Testing (on Squarespace Temporary URL)

#### Content Verification
- [ ] All pages have correct content
- [ ] All text is accurate and properly formatted
- [ ] Headings are properly structured (H1, H2, H3)
- [ ] All images are uploaded and displaying correctly
- [ ] Church logo displays correctly
- [ ] Footer logos (ADGL, ACNA) display correctly
- [ ] Special announcements are visible and styled correctly

#### Links Testing
- [ ] All internal links work (Home, About, Contact navigation)
- [ ] All external links work:
  - [ ] Google Maps link
  - [ ] ADGL website
  - [ ] ACNA website
  - [ ] Book of Common Prayer link
  - [ ] Facebook page
  - [ ] YouTube channel
- [ ] Phone number is clickable (tel: link)
- [ ] Email address is clickable (mailto: link)
- [ ] Social media icons link correctly

#### Functionality Testing
- [ ] Contact form submits successfully
- [ ] Contact form sends email to StMatthewsACT@gmail.com
- [ ] Contact form confirmation message displays
- [ ] Navigation menu works on desktop
- [ ] Mobile hamburger menu works
- [ ] All buttons/CTAs are clickable
- [ ] Google Maps embed loads and is interactive

#### Design & Visual Testing
- [ ] Colors match original site (burgundy and gold)
- [ ] Fonts are appropriate and readable
- [ ] Logo displays at correct size
- [ ] Footer looks correct
- [ ] Worship service callout box is prominent
- [ ] Special announcements are visually distinct
- [ ] Overall layout matches intended design
- [ ] No broken images
- [ ] No missing content

#### Mobile Responsiveness
Test on multiple devices:
- [ ] iPhone (Safari)
- [ ] Android phone (Chrome)
- [ ] iPad/tablet
- [ ] Content is readable on mobile
- [ ] Images scale properly
- [ ] Navigation works (hamburger menu)
- [ ] Contact form works on mobile
- [ ] Phone number is tap-to-call
- [ ] Email is tap-to-email
- [ ] No horizontal scrolling
- [ ] Text is large enough to read
- [ ] Buttons/links are easy to tap

#### Browser Testing
Test on multiple browsers:
- [ ] Chrome (Windows & Mac)
- [ ] Firefox
- [ ] Safari (Mac)
- [ ] Edge
- [ ] Mobile Safari (iOS)
- [ ] Mobile Chrome (Android)

#### Performance Testing
- [ ] Pages load quickly (under 3 seconds)
- [ ] Images are optimized (not too large)
- [ ] No console errors (check browser developer tools)
- [ ] Lighthouse score (Google Chrome DevTools):
  - [ ] Performance: 80+
  - [ ] Accessibility: 90+
  - [ ] SEO: 90+

#### SEO Testing
- [ ] Page titles are set correctly
- [ ] Meta descriptions are set
- [ ] Images have alt text
- [ ] Headings are properly structured
- [ ] URLs are clean and readable
- [ ] Favicon displays in browser tab
- [ ] Social sharing image is set

#### Accessibility Testing
- [ ] All images have alt text
- [ ] Color contrast is sufficient
- [ ] Links are clearly identifiable
- [ ] Forms have proper labels
- [ ] Site is keyboard navigable (tab through all links)
- [ ] Screen reader friendly (test with browser screen reader)

---

## 10. Launch Checklist

### Final Pre-Launch Tasks

#### 1 Week Before Launch
- [ ] Complete all testing from Testing Checklist
- [ ] Get final approval on content from church leadership
- [ ] Verify all contact information is correct
- [ ] Prepare launch announcement for social media
- [ ] Notify key stakeholders of launch date
- [ ] Set up Google Analytics (if using)
- [ ] Create backup of current Hugo site

#### 24-48 Hours Before Launch
- [ ] Lower DNS TTL to 300 seconds (if not already done)
- [ ] Double-check all content one final time
- [ ] Verify contact form works
- [ ] Test from multiple devices
- [ ] Prepare DNS changes (but don't apply yet)

#### Launch Day

**Morning:**
- [ ] Final content review
- [ ] Test contact form one more time
- [ ] Verify no broken links
- [ ] Screenshot old site for records

**Launch Sequence:**

1. [ ] Update DNS records at domain registrar
   - Point A record to Squarespace
   - Update CNAME for www
   - Keep MX records if using domain email

2. [ ] Verify DNS propagation begins
   - Use: whatsmydns.net
   - Check from different locations

3. [ ] Monitor email for contact form submissions

4. [ ] Check site on new domain
   - Test all pages
   - Test all links
   - Test contact form

5. [ ] Enable SSL/HTTPS (if not auto-enabled)
   - Settings → SSL → Enable Secure (HTTPS)
   - Force HTTPS

**Within 2-4 Hours:**
- [ ] Verify site loads on new domain
- [ ] Test from multiple devices
- [ ] Check mobile version
- [ ] Test contact form on live domain

**Within 24 Hours:**
- [ ] Post announcement on social media
- [ ] Send email to congregation (if applicable)
- [ ] Monitor contact form submissions
- [ ] Check analytics/traffic

### Rollback Plan (If Issues Occur)

**If major issues are discovered:**

1. **Revert DNS immediately**
   - Change DNS back to old hosting (Netlify)
   - Takes 5 minutes to 4 hours to propagate

2. **Investigate issues on Squarespace staging URL**
   - Fix problems on yoursite.squarespace.com
   - Re-test thoroughly

3. **Re-launch when issues are resolved**

---

## 11. Post-Migration Tasks

### Immediate (First Week)

- [ ] Monitor contact form submissions daily
- [ ] Check Google Search Console for crawl errors
- [ ] Submit sitemap to Google Search Console
- [ ] Monitor site analytics
- [ ] Test site functionality daily
- [ ] Address any issues that arise
- [ ] Gather feedback from church members

### First Month

- [ ] Review analytics data
- [ ] Check search engine rankings
- [ ] Verify all pages are indexed by Google
- [ ] Update any external listings with new site (if applicable)
- [ ] Consider adding blog/news section (optional)
- [ ] Add any seasonal/event content
- [ ] Review and optimize images if needed
- [ ] Set up Google My Business (if not already done)

### Setting Up Contributors

**For Basic Plan (2 contributors maximum):**
You can add 1 additional person besides yourself. Go to Settings → Permissions → Invite Contributor.

**For Core Plan (unlimited contributors):**
If you chose the Core plan, here's how to add team members:

1. **Add Contributors**
   - Go to Settings → Permissions
   - Click "Invite Contributor"
   - Enter their email address
   - Choose permission level

2. **Permission Levels to Consider**
   - **Website Editor** - Can edit pages and blog posts (recommended for most volunteers)
   - **Administrator** - Full access except billing (for trusted staff)
   - **Comment Moderator** - Can moderate comments only
   - **Analytics** - Can view analytics only
   - **Billing** - Can manage billing (church treasurer)

3. **Recommended Setup for Church**
   - Pastor: Administrator
   - Church staff: Website Editor or Administrator
   - Volunteers: Website Editor (limited to specific pages if needed)
   - Treasurer: Billing permission

4. **Best Practices**
   - Remove contributors who no longer need access
   - Review permissions quarterly
   - Use Website Editor for most people (limits damage from mistakes)
   - Keep Administrator access limited to 2-3 trusted people

### Ongoing Maintenance

**Monthly:**
- [ ] Review analytics
- [ ] Update content as needed
- [ ] Check for broken links
- [ ] Test contact form
- [ ] Update special announcements/events

**Quarterly:**
- [ ] Review and update all content
- [ ] Check mobile experience
- [ ] Review SEO performance
- [ ] Update photos if desired
- [ ] Review contributor permissions

**Annually:**
- [ ] Renew Squarespace subscription
- [ ] Comprehensive content audit
- [ ] Review design and consider updates
- [ ] Update pastor bio/photos if needed
- [ ] Audit all contributor accounts

### Decommissioning Old Site

**After 30 Days of Successful Operation:**

1. [ ] Archive Hugo site locally
   - Download full backup
   - Store in safe location
   - Keep for reference/records

2. [ ] Cancel Netlify hosting (if paid)
   - Or keep as archive (free tier available)

3. [ ] Archive GitHub repository
   - Mark as archived
   - Keep for historical reference

4. [ ] Update bookmarks/documentation
   - Remove references to old build process
   - Update internal documentation

---

## Appendix

### A. Important Squarespace Resources

**Documentation:**
- Squarespace Help Center: https://support.squarespace.com
- Template Guide: https://support.squarespace.com/hc/en-us/sections/206670347
- Domain Help: https://support.squarespace.com/hc/en-us/sections/206670427

**Community:**
- Squarespace Forum: https://forum.squarespace.com
- Squarespace Circle: https://circle.squarespace.com (for professionals)

**Support:**
- Live chat: Available in Squarespace dashboard
- Email: support@squarespace.com
- Phone: 1-646-580-3456 (24/7)

### B. Hugo Site Technical Details

**Current Hosting:**
- Platform: Netlify
- Domain: stmatthewstoledo.org
- Hugo Version: 0.140.2

**Build Commands:**
- Production: `hugo --gc --minify`
- Preview: `hugo --gc --minify --buildFuture -b $DEPLOY_PRIME_URL`

**Current Repository:**
- Location: (Git repository location)
- Branch: main

### C. Contact Information Quick Reference

**Website:**
- Domain: stmatthewstoledo.org
- Email: StMatthewsACT@gmail.com
- Phone: (567) 343-0757

**Meeting Location:**
- Toledo First Seventh-day Adventist Church
- 4909 W. Sylvania Ave.
- Toledo, OH 43623

**Service Times:**
- Sunday: 10:00 AM
- Children's Ministry: During 10:00 AM service

**Pastor:**
- Father Zeke Coughlin, Rector

**Affiliations:**
- Anglican Diocese of the Great Lakes (ADGL)
- Anglican Church in North America (ACNA)

### D. Squarespace Limitations to Be Aware Of

**Compared to Hugo:**
- Less control over code/HTML
- Cannot use version control (Git) directly
- Limited to Squarespace's templates and customization options
- Monthly cost vs. free Hugo hosting

**Advantages of Squarespace:**
- No technical knowledge required for updates
- Built-in hosting and SSL
- Integrated contact forms
- Professional support available
- Mobile app for quick updates
- Built-in analytics
- Easy for non-technical staff to manage
- **Multiple contributors** (with Core plan) - Perfect for church teams where pastor, staff, and volunteers can all help maintain the site

### E. Future Enhancement Ideas

**Consider Adding Later:**
- **Blog/News Section** - Share updates, sermons, announcements
- **Events Calendar** - Squarespace has built-in events
- **Photo Gallery** - Share photos from church events
- **Sermon Archive** - Audio or video sermons
- **Online Giving** - Donation functionality (Business plan required)
- **Member Directory** - Password-protected (if desired)
- **Prayer Request Form** - Additional contact form
- **Newsletter Signup** - Email list integration

---

## Summary

This migration guide provides comprehensive instructions for transitioning from Hugo to Squarespace. The process involves:

1. **Planning** (1-2 weeks) - Account setup and template selection
2. **Migration** (2-4 weeks) - Content transfer and design implementation
3. **Testing** (1 week) - Thorough testing before launch
4. **Launch** - DNS update and go-live
5. **Post-Migration** - Monitoring and ongoing maintenance

**Key Success Factors:**
- Thorough testing before launch
- Clear timeline and milestones
- Complete content inventory
- DNS backup plan
- Post-launch monitoring

**Estimated Total Time:** 4-7 weeks from start to launch

**Plan Recommendation:**
- Basic Plan ($16/month) if only 1-2 people need website access
- Core Plan ($23/month) if 3+ contributors or advanced features needed

---

## Questions or Issues?

If you encounter problems during migration:
1. Check Squarespace Help Center
2. Contact Squarespace Support (24/7)
3. Post in Squarespace Forum
4. Consider hiring a Squarespace expert

**Good luck with your migration!**

---

## Sources and References

This guide was researched and verified using the following sources (December 2025):

### Squarespace Pricing and Plans:
- [Squarespace Pricing Update (2025): New Plans & Costs](https://www.squarepros.io/blog/squarespace-pricing-2025)
- [Squarespace Pricing and Fees (2025) — Which Plan Is Best?](https://www.stylefactoryproductions.com/squarespace-pricing)
- [Squarespace Pricing in 2025 Explained: Which Plan Is Best for Your Business?](https://launchhappy.co/guides/squarespace-pricing-explained)

### Domain Transfer and Connection:
- [Transferring a domain to a Squarespace site – Squarespace Help Center](https://support.squarespace.com/hc/en-us/articles/206542037-Transferring-a-domain-to-a-Squarespace-site)
- [Domain transfer timing – Squarespace Help Center](https://support.squarespace.com/hc/en-us/articles/115011719247-Domain-transfer-timing)
- [Transferring vs. connecting domains – Squarespace Help Center](https://support.squarespace.com/hc/en-us/articles/115002755267-Transferring-vs-connecting-domains)
- [How to Transfer Domain to Squarespace [2025 Guide]](https://litextension.com/blog/transfer-domain-to-squarespace/)

### Templates:
- [Squarespace Template Families and Templates](https://www.squareexperts.com/news/squarespace-template-families-and-templates)
- [Version 7.0 templates – Squarespace Help Center](https://support.squarespace.com/hc/en-us/sections/4415397925901-Version-7-0-templates)
- [14 All-Time Best Squarespace Templates (2025 Edition)](https://www.sqspthemes.com/blog/best-squarespace-templates)

### Email and Google Workspace:
- [Google Workspace pricing, billing, and invoices – Squarespace Help Center](https://support.squarespace.com/hc/en-us/articles/205812258-Google-Workspace-pricing-billing-and-invoices)
- [Free Google Workspace offer – Squarespace Help Center](https://support.squarespace.com/hc/en-us/articles/206537337-Free-Google-Workspace-offer)
- [How Much Is Squarespace Email?](https://www.sqspthemes.com/squarespace-faqs/how-much-is-squarespace-email)

### Contributors and Collaboration:
- [Squarespace permissions explained – Squarespace Help Center](https://support.squarespace.com/hc/en-us/articles/206537297-Squarespace-permissions-explained)
- [Contributors basics – Squarespace Help Center](https://support.squarespace.com/hc/en-us/articles/115010355107-Contributors-basics)
- [How to Add a Contributor to Your Squarespace Website (2025)](https://www.squarepros.io/blog/add-contributor-to-squarespace-website)
- [Squarespace Personal vs Business: Which Better Suits You? [2025]](https://litextension.com/blog/squarespace-personal-vs-business/)

### Official Squarespace Resources:
- [Squarespace Official Website](https://www.squarespace.com)
- [Squarespace Help Center](https://support.squarespace.com)
- [Squarespace Domain Services](https://domains.squarespace.com/transfer-a-domain)

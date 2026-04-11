# DFRRF 101 — Member Education Website

A static website providing plain-language pension education for members of the Denton Firemen's Relief and Retirement Fund (DFRRF).

**Live URL:** https://dentonfire.github.io/Pension/

---

## Project Overview

DFRRF 101 is a member-facing educational resource that explains how the Denton firefighter pension works, who manages it, and where members can access their benefits. The site is designed to be:

- **Accessible:** Plain language, no jargon, mobile-friendly
- **Authoritative:** Accurate benefit information with citations to governing documents
- **Low-maintenance:** Static HTML with no backend dependencies

The site complements (but does not replace) the official pension portal at dentonfirepension.com.

---

## File Structure

```
/
├── index.html          # Home page (DFRRF 101 overview)
├── Team.html           # Board of Trustees and Service Providers
├── Documents.html      # Document Library (Plan Document, IPS, etc.)
├── Newsletter.html     # Newsletter signup and archive
├── dfd-crest.png       # DFD logo (flags, courthouse, maltese cross)
└── README.md           # This file
```

All pages are self-contained HTML files with embedded CSS. No external stylesheets or JavaScript libraries required.

---

## Pages

### index.html (Home)
The main educational content:
- What is the DFRRF (defined benefit overview)
- Key fund statistics (assets, funded ratio, amortization period)
- History of TLFFRA and the PRB
- Benefit formula explanation (2.59% rate)
- DFRRF vs. TMRS vs. 401(k) comparison
- Links to calculator and newsletter signup

### Team.html
Board and service provider directory:
- Seven Board of Trustees members with photos
- Gary Calmes (Fund Administrator) and Bill Coleman (Investment Advisor) featured prominently
- Additional service providers: Recording Secretary, Actuary, Custodian, Property Manager

### Documents.html
Links to governing documents:
- Plan Document (via pension portal)
- Investment Policy Statement
- Meet and Confer Agreement (Ordinance 2023-1643)
- TLFFRA statute
- 2026 TLFFRA Report

### Newsletter.html
Newsletter information:
- Signup link (Constant Contact)
- Archive of past issues
- Contact information for Gary Calmes

---

## Design System

### Colors
| Name | Hex | Usage |
|------|-----|-------|
| Navy | #1a2744 | Primary brand, headers, nav |
| Navy Light | #243352 | Gradients, footer |
| Gold | #c8a84e | Accents, borders, CTAs |
| Gold Light | #e8d08e | Gradient highlights |
| Cream | #faf8f2 | Page background |
| Warm Gray | #f0ece4 | Card backgrounds, alternating rows |
| Text | #2c2c2c | Body text |
| Text Light | #5a5a5a | Secondary text, labels |

### Typography
- **Headings:** Merriweather (Google Fonts), serif
- **Body:** Source Sans 3 (Google Fonts), sans-serif
- **Fallbacks:** Georgia, Segoe UI, system fonts

### Components
- **Stat cards:** Hover lift effect with gold border highlight
- **Info boxes:** Left border accent (gold or navy)
- **Team cards:** Rectangular photos (210×270px) with rounded corners
- **Navigation:** Fixed top bar with slide-out drawer on mobile
- **QR FAB:** Floating button in bottom-right for quick site sharing

### Logo Usage
- **dfd-crest.png:** Full logo with American flag, Texas flag, Denton County Courthouse, maltese cross, Star of Life, and "1874" banner
- **Hero section (index.html):** Positioned left side, 180px wide
- **Page headers (subpages):** Centered, 100px wide
- **Watermark:** Centered fixed background, 4% opacity
- **Favicon:** Separate DFD badge hosted on Constant Contact CDN
- **Navbar brand:** 34×34px square badge (Constant Contact CDN)

---

## External Dependencies

### Hosted Resources
| Resource | Host | URL |
|----------|------|-----|
| Merriweather font | Google Fonts | fonts.googleapis.com |
| Source Sans 3 font | Google Fonts | fonts.googleapis.com |
| Favicon | Constant Contact | files.constantcontact.com/3720c3fd901/10017eb4-f7d2-424d-92ed-c1b5424b9869.png |
| Trustee photos | Constant Contact | files.constantcontact.com/3720c3fd901/... |
| QR code | QR Server API | api.qrserver.com |

### Linked External Sites
- **Pension Portal:** dentonfirepension.com
- **Retirement Calculator:** dentonfire.github.io/Denton_Firemen-s_Pension/
- **Newsletter Signup:** lp.constantcontactpages.com/sl/YZDxyEQ/pension
- **Newsletter Archive:** conta.cc/3PPN0Qf (Issue #1)
- **PRB Data:** data.prb.texas.gov, prb.texas.gov
- **TEXPERS:** texpers.org
- **City of Denton Documents:** lfpubweb.cityofdenton.com

---

## Deployment

### GitHub Pages (Current)
The site is deployed via GitHub Pages from the `dentonfire/Pension` repository.

To deploy updates:
1. Clone or pull the repository
2. Replace files with updated versions
3. Commit and push to the `main` branch
4. GitHub Pages automatically rebuilds (usually within 1-2 minutes)

### Manual Deployment
For other hosting environments:
1. Upload all HTML files and `dfd-crest.png` to the web root
2. Ensure the server serves `.html` files with `text/html` content type
3. No server-side processing required

---

## Content Maintenance

### Updating Fund Statistics
Key statistics appear on the home page (index.html):
- **Total Fund Assets:** Update the `~$187M` figure as reported
- **Funded Ratio:** Currently 91.2% (12/31/2023 valuation)
- **Amortization Period:** Currently 6.5 years
- **Benefit Rate:** 2.59% (this is set by Plan Document and rarely changes)

### Updating Board Members
Edit Team.html to add, remove, or update trustees. Each trustee card follows this structure:
```html
<div class="team-card">
  <div class="team-avatar">
    <img src="[PHOTO_URL]" alt="[NAME]">
  </div>
  <div class="team-name">[NAME]</div>
  <div class="team-role">[ROLE]</div>
</div>
```

Photos should be hosted on Constant Contact or another reliable CDN.

### Adding Newsletter Issues
Edit Newsletter.html to add new issues to the archive:
```html
<div class="newsletter-issue">
  <div class="issue-info">
    <div class="issue-num">Issue #[N]</div>
    <div class="issue-title">[TITLE]</div>
    <div class="issue-desc">[DESCRIPTION]</div>
  </div>
  <a href="[CONSTANT_CONTACT_URL]" target="_blank" rel="noopener" class="issue-link">Read Issue &#8599;</a>
</div>
```

### Updating Documents
Edit Documents.html to add or update document links. Use the `doc-card` component:
```html
<a class="doc-card" href="[URL]" target="_blank" rel="noopener">
  <div class="doc-icon pdf">PDF</div>
  <div>
    <div class="doc-title">[TITLE]</div>
    <div class="doc-desc">[DESCRIPTION]</div>
  </div>
</a>
```

---

## Key Information References

### Benefit Formula
```
Monthly Benefit = Years of Service × 2.59% × Final Average Salary ÷ 12
```
- **Benefit Rate:** 2.59% per year of service (Plan Document Section B.2, effective January 1, 2011)
- **Final Average Salary (FAS):** Average of highest 36 consecutive months
- **Portal displays 2.55%:** This is a known software error; 2.59% is correct

### Contribution Rates
- **Member contribution:** 12.6% of compensation (paycheck deduction)
- **City contribution:** 18.5% of compensation (separate, paid by City)
- **Total:** 31.1% of compensation

### Retirement Eligibility
- **Normal retirement:** Age 50 with 20 years of service
- **Vesting:** 10 years for partial benefit
- **Retro DROP:** Available at age 52 with 22 years; max 48 months

### Social Security
Denton firefighters DO participate in Social Security. The DFRRF pension is in addition to Social Security, not a replacement.

---

## Board of Trustees (Current)

| Name | Role |
|------|------|
| Gerrad Friend | Chair |
| Derek Oswald | Vice Chair |
| Hunter Lott | Secretary |
| Dick Smith | Trustee |
| Charlie Parker | Trustee |
| Tony Clark | Mayor's Appointee |
| Matthew Hamilton | Director of Finance |

**Board meetings:** Third Wednesday of each month, 8:30 AM, Central Fire Station (332 E. Hickory St., Denton)

---

## Service Providers (Current)

| Role | Provider |
|------|----------|
| Fund Administrator | Gary Calmes |
| Investment Advisor | Bill Coleman, Garnett Advisors, LLC |
| Recording Secretary | Sarah Lollar |
| Actuary | Mark Fenlaw, Rudd & Wisdom, Inc. |
| Custodian | Frost Bank |
| Property Manager | Rebecca Andreasen, NorthBridge Management |

---

## Contact

**Fund Administrator:** Gary Calmes  
**Email:** gary@dentonfirepension.com  
**Pension Portal:** https://dentonfirepension.com/Home.aspx

---

## Legal Disclaimer

This website is for educational purposes only. It is not a legal summary of plan provisions. In the event of any conflict between this website and the official Plan Document, the Plan Document controls.

---

## Version History

| Date | Changes |
|------|---------|
| April 2026 | Initial release with 4-page site structure |
| April 2026 | Updated branding with DFD crest logo |
| April 2026 | Reorganized Team page with rectangular photo layout |

---

## Credits

**Content & Design:** Hunter Lott, DFRRF Secretary  
**Hosted on:** GitHub Pages  
**Newsletter Platform:** Constant Contact

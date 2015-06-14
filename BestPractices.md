# Best Practices in Cartographic Accessibility

It is estimated that 20% of the population has a disability with 8.5% of the population having a disability that directly impacts their use on a computer. While not all disabilities make internet use difficult for these populations a large proportion of people are affected in some way. 

For schools, universities, and government organizations it would not only be unwise to avoid these populations, but in many cases, it would also violate the law while designing content for public consumption.

However, best practices in accessibility can impact **_all_** users in a good way. For example, Apple's iPhone has been designed with accessibility in mind but has created a better experience for all of its users over time.

Listed below is a set of guidelines for developers, cartographers, GIS specialists, geographers, and civic hackers to consider when creating projects that include static and interactive web maps.

## Introduction:
**_Web accessibility benefits everybody._** Your map or site can be compliant and technically accessible yet functionally inaccessible. Just because your map and/or website is accessible **_does not_** mean that is it usable. Ensure your content is usable first, then focus on making it accessible to your audience. 

**_It's an imperfect world; if your goal is 100% total accessibility before you begin, you have already failed:_** Perfection is unattainable but do *the best of your ability* to make content available to the widest selection of users as possible. To do so, consider accessibility and usability as part of the same conversation.


### Table of Contents:
- [Section I. Key Takeaways](#section1)  
- [Section II. Types of Disabilities](#section2)  
- [Section III. Accessibility Principles](#section3)
- [Section IV. Accessibility Techniques](#section4)
- [Section V. International Laws and Standards](#section5)  
- [Section VI. Resources](#section6) 


<a name="section1">
## Section I. Key Takeaways:</a>
1. Focus on the purpose of the map, what story are you trying to tell? 
2. Something that is dead on mobile, is dead. 
3. Usability first, accessibility next.  
4. Simplicity is best, don't force it. Keep asking: Does everybody need this?
5. Accessibility is about people. Only people can evaluate true accessibility. WAVE can help facilitate human interaction but it is not the catch-all answer.  
6. Enable the experience, don't make the experience.  
7. Keyboard user != Screen reader user, but Keyboard user ≈ Screen reader user.  
8. There are some things you just can't make accessible.


<a name="section2" />
## Section II. Types of Disabilities:</a>

The four major categories of disability types are:

### 1. Visual:
Blindness, low-vision, color-blindness.

### 2. Hearing:
Deafness and hard-of-hearing.

### 3. Motor:
Inability to use a mouse, slow response time, limited fine motor control, Repetition is difficult for these audiences and fatigue is exhibited frequently (i.e. Cerebral Palsy, complete paralysis).

### 4. Cognitive: 
**The largest disability group** which varies greatly and includes: learning disabilities, distractibility, and the inability to remember or focus on large amounts of information. Consistent and simple organization goes a long way with these audiences and focusing on the important content.


<a name="section3"/>  
## Section III. Accessibility Principles:</a>
#### 1. Assign alternative text *[static and interactive maps]*:
Alternative text provides a textual alternative to non-text content in web pages (i.e. static maps, and/or images). Alternative text is especially helpful for people who are blind and rely on a screen reader to have the content of the website read to them.

When using alternative text, describe the **_content and function_** providing a semantic meaning and description of the images, which is also used by search engines. For example, if you have a thumbnail of a regional park map you could label the image alternative text to reflect the content of the image (i.e. `<alt="Regional park map">`).

However, not all images are as clear cut. For example, if you have an image of a girl that is being used as context of human health an alternative text of `<alt="girl">` isn't helpful for those with screen readers. In fact, there is no right answer in this case as it is difficult to provide content and/or function to a screen reader so in the case `<alt="">` may be the best option.

#### 2. Implement an appropriate document structure *[interactive maps]*:
Headings, lists, and other structural elements provide meaning and structure to web pages. Also, **_headings should never be empty_** as empty headings cannot be read by a screen reader. Headings are a key component as they are also read by search engines and can help direct **all** users to your site.

**_Don't skip heading levels:_** The document structure can also facilitate keyboard navigation within the page. For example, don't skip from a `<h1>` tag to a `<h3>` tag without using a `<h2>` tag in between the two. Blind users with screen readers have a difficult time navigating through content when a solid document structure is not set in place. In addition to serving those that are blind, document structure helps organize a page for other users and helps you maintain the page in the future. 

**_However, you can skip backward_** For example, if you have already labeled your heading tags `<h1>`, `<h2>`, `<h3>`, and `<h4>` then you can skip to a `<h3>` tag without labeling the `<h1>` or `<h2>` tags since they are shown earlier in your code.

#### 3. Provide titles and/or headers for data tables *[static and interactive maps]*:
Try and refrain from using tables as a layout and use them **_strictly_** to display data that are **logical** and **intuitive**. Tables that are used to organize tabular data should have appropriate table headers (the `<th>` element). For example:

<table>
<caption>Shelly's Daughters</caption>
<tr>
<th scope="col">Name</th>
<th scope="col">Age</th>
<th scope="col">Birthday</th>
</tr>
<tr>
<th scope="row">Jackie</th>
<td>5</td>
<td>April 5</td>
</tr>
<tr>
<th scope="row">Beth</th>
<td>8</td>
<td>January 14</td>
</tr>
</table>

Data cells should be associated with their appropriate headers, making it easier for screen reader users to navigate and understand the data table using `scope` in the table headers and values. For example:

	<table>  
	<caption>Shelly's Daughters</caption>  
	<tr>  
	<th SCOPE="col">Name</th>  
	<th SCOPE="col">Age</th>  
	<th SCOPE="col">Birthday</th>  
	</tr>  
	<tr>  
	<th SCOPE="row">Jackie</th>  
	<td>5</td>  
	<td>April 5</td>  
	</tr>  
	<tr>  
	<th SCOPE="row">Beth</th>  
	<td>8</td>  
	<td>January 14</td>  
	</tr>  
	</table> 

#### 4. Ensure links make sense out of context *[interactive maps]*:
Every link should make sense if the link text is read by itself. Screen reader users may choose to read only the links on a web page. Certain phrases like "click here" and "more" **_must_** be avoided.  

#### 5. Ensure accessibility of non-HTML content (e.g. PDF files, Microsoft Word documents, and PowerPoint presentations) *[static maps]*:
In addition to all of the other principles, PDF documents and other non-HTML content **_must be as accessible as possible_**. 

If you cannot make it accessible, consider using HTML instead or, at the very least, provide an accessible alternative. PDF documents should also include a series of tags, with organization, to make it more accessible. A tagged PDF file looks the same, but it is almost always more accessible to a person using a screen reader.

#### 6. Allow users to skip repetitive elements on the page *[interactive maps]*:
You should provide a method that allows users to skip navigation or other elements that repeat on every page. This is usually accomplished by providing a **"Skip to Main Content"** or **"Skip Navigation"** link at the top of the page which jumps to the main content of the page. The "Skip to" navigation allows those with screen readers to get to content easily instead of having to tab through many non-relevant pieces of information. **_Note: Half of skip links don't work as a CSS element of `display:none` disables the skip to content or the `<div id>` has changed over time._**   

If you have data that can be displayed in a table that is provided with your map, you can created a **"Skip to Table"** option to your users.

In addition, ensure **all** content can be accessed without the use of a mouse, use `tab` and directional keyboard buttons (`>` and `<`) to test your application. **_An application should have as much of the same content available to the largest audience as possible._**

#### 7. Do not rely on color alone to convey meaning *[static and interactive maps]*:
The use of color can enhance comprehension, but do not use color alone to convey information. That information may not be available to a person who is colorblind and will be unavailable to screen reader users. 

**_Contrast impacts everybody_**. Common sense is vital when considering color contrast, if you can't differentiate the colors - nobody else will.

In order to showcase additional meaning, you can:

- Use simple, high-contrast color schemes.  
- Consider patterns, line widths, etc.
  
#### 8. Ensure content is clearly shown and/or written and easy to read *[static and interactive maps]*:

- Write clearly 
- Use [clear fonts](http://webaim.org/techniques/fonts), *WebAIM resource*
- Use [headings and lists](http://webaim.org/techniques/semanticstructure) appropriately, *WebAIM resource*


#### 9. Make sure content is clearly shown *[static and interactive maps]*:
- Number of layers:
	- Err on the side of too few layers (i.e. 3-4 per map). 
	- When in doubt, leave it out!
- Layer Zooming:
	- Display layer data in a way that is appropriate for the zoom level.
	- Hide and display geographic details as appropriate.

#### 10. Make JavaScript as accessible as possible *[interactive maps]*:
Make your best effort to ensure that [JavaScript event handlers](http://webaim.org/techniques/javascript/eventhandlers) are device independent (i.e. events do not require the use of a mouse) and that your page does not rely on JavaScript to function. (**_Note:_** This is not always possible with interactive maps but make your best effort while designing your map if other alternatives are possible).

#### 11. Design to standards *[static and interactive maps]*:
HTML-compliant and accessible pages are more robust and provide better search engine optimization. [Cascading Style Sheets](http://webaim.org/techniques/css) (CSS) allow you to separate content from presentation. This provides more flexibility and accessibility of your content.

#### 12. Supplement a visual display with a table or list *[static and interactive maps]*:
Remember that people have different ways of orienting themselves and absorbing geographic information. Don't let the map be your only format for data display, supplement your map with a table and/or list (i.e. directions/routing, data display, etc.).

Adding additional content in the form of a table or list for users also provides another resource to blind, and even colorblind users when maps are involved. In this way a larger proportion of your audience can benefit from the content you are displaying, including users who may not be visually impaired at all.


<a name="section4"/>  
## Section IV: Accessibility Techniques:</a>

#### Code Snippets:

1. **Avoid using the following CSS:** `a { outline: 0; }` or  `a { outline: none; }`
2. **Avoid using empty `<th>`**
3. **Use the following code:** Set the hover and focus CSS transitions equal to each other (`a:hover, a:focus`). The hover and focus should have the same functionality throughout an application.

#### Samples of Accessible Maps:
*Coming soon!*

#### Templates
*Coming soon!*


<a name="section5"/>  
## Section V. International Laws and Standards:</a>
### Australia:
- [Disability Discrimination Act](http://www.austlii.edu.au/au/legis/cth/consol_act/dda1992264) (DDA) of 1992
- [World Wide Web Access: Disability Discrimination Act Advisory Notes](http://www.hreoc.gov.au/disability_rights/standards/www_3/www_3.html), version 3.2 *(August 2002)*

### Canada:
- [Canadian Human Rights Act](http://laws.justice.gc.ca/en/H-6/243963.html) of 1977
- [Ontarians with Disailities Act](http://www.e-laws.gov.on.ca/DBLaws/Statutes/English/01o32_e.htm) of 2001
- [Government of Canada Internet Guide](http://www.gol-ged.gc.ca/index_e.asp)
- [Canada's Common Look and Feel Guidelines](http://www.tbs-sct.gc.ca/clf-nsi/index_e.asp)
	- [Provisions for accessibility](http://www.tbs-sct.gc.ca/clf-nsi/inter/inter-01-tb_e.asp)

### Germany:
- [Federal Ordinance on Barrier-Free Information Technology](http://www.einfach-fuer-alle.de/artikel/bitv_english)

### Ireland:
- [Irish National Disability Authority IT Accessibility Guidelines](http://www.accessit.nda.ie/policy_and_legislation.html)

### Japan:
- [Web Access by People with Disabilities](http://www.legco.gov.hk/yr00-01/english/panels/itb/papers/a774-02e.pdf) *(March 12, 2001)*
- [Government concerns about enhancing web accessibility](http://www.info.gov.hk/gia/general/200109/30/0929144.htm), *Press release*
- [Basic Law on the Formation of an Advanced Information and Telecommunications Network Society](http://www.kantei.go.jp/foreign/it/it_basiclaw/it_basiclaw.html) *(January 6, 2001)*

### New Zealand:
- [E-Government Initiative of New Zealand](http://www.e-government.govt.nz/) (web guidelines)

### Portugal:
- [Accessibility of Public Administration Web Sites for Citizens with Special Needs](http://www.acesso.umic.pcm.gov.pt/acesso/res9799_en.htm)

### United Kingdom:
- [Disability Discrimination Act (DDA)](http://www.hmso.gov.uk/acts/acts1995/Ukpga_19950050_en_1.htm) of 1995
- [Accessibility as a legal requirement in UK](http://lists.w3.org/Archives/Public/w3c-wai-ig/2003JanMar/0022.html) *(October 1, 1999)*
- [Special Educational Needs and Disability Act](http://www.hmso.gov.uk/acts/acts2001/20010010.htm) of 2001
- [Disability Rights Commission (DRC) Code of Practice](http://www.drc-gb.org/uploaded_files/documents/2008_223_drc_cop_rights_of_Access.doc)

###United States of America: 
- [The Americans with Disabilities Act (ADA)](http://webaim.org/articles/laws/usa/ada)*, WebAIM summary*  
- [Rehabilitation Act of 1973](#)
	- [Section 504](http://www.dol.gov/oasam/regs/statutes/sec504.htm)
	- [Section 508](http://www.section508.gov)  


<a name="section6"/>  
## Section VI. Resources:</a>
### Cartography:
- [Why Website Design Needs to Go Beyond Color](http://mashable.com/2014/04/22/web-designing-colorblindness) (Mashable article)

### Browser Extensions:
- Accessibility Developer Tools ([Chrome](https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb))
- ChromeVox ([Chrome](https://chrome.google.com/webstore/detail/chromevox/kgejglhpjiefppelpmljglcjbhoiplfn))
- Color Contrast Analyzer ([Chrome](https://chrome.google.com/webstore/detail/color-contrast-analyzer/dagdlcijhfbmgkjokkjicnnfimlebcll))
- Color Enhancer ([Article](http://www.cio.com/article/2919589/chrome/this-chrome-extension-helps-color-blind-users-see-the-web.html), [Chrome](https://chrome.google.com/webstore/detail/color-enhancer/ipkjmjaledkapilfdigkgfmpekpfnkih))
- ColorZilla (Firefox, [Chrome](https://chrome.google.com/webstore/detail/colorzilla/bhlhnicpbhignbdhedgjhgdocnmhomnp))
- NoCoffee ([Chrome](https://chrome.google.com/webstore/detail/nocoffee/jjeeggmbnhckmgdhmgdckeigabjfbddl))
- WAVE Evaluation Tool ([Chrome](https://chrome.google.com/webstore/detail/wave-evaluation-tool/jbbplnpkjmmeebjpijfedlgcdilocofh))

### Color Blindness:
- [Color Brewer](http://colorbrewer2.org) 
- [Color Oracle](http://www.colororacle.org) (software download)
- [Color Picker for Data](http://tristen.ca/hcl-picker)

### Color Contrast:
- [Colorable](http://jxnblk.com/colorable)
- [Tangaru Contrast-Finder](http://contrast-finder.tanaguru.com)

### General Web:
- [Accessibility in User-Centered Design Using Personas](http://www.uiaccess.com/accessucd/personas.html)
- [WebAIM](http://webaim.org)
- [Web Content Accessibility Guidelines](http://www.w3.org/TR/WCAG20) (WCAG 2.0)
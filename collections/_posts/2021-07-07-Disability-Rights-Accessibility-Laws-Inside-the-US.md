---
SPDX-FileCopyrightText: 2022 Cam Coulter <git@camcoulter.com>
SPDX-License-Identifier: CC-BY-SA-4.0
layout: post
title: "Disability Rights & Accessibility Laws, Inside the United States"
published: true
date: 2021-07-07 18:41
date_updated: 2021-07-22 19:28
categories:
- accessibility
tags:
- 100 Days of A11y
description: "Inside the United States, what rights do people with disabilities have and what laws mandate accessibility?"
image: a11y
toc: true
---

## Introduction
{: tabindex="-1"}

I'm probably going into this in greater detail than the CPACC exam requires, but this stuff is important, I enjoy geeking out about it, and doing all this research and writing this all out really helps me understand these laws much better.

Inside the United States, what rights do people with disabilities have and what laws mandate accessibility?

## Federal Laws
{: tabindex="-1"}

### The Fair Housing Act
{: tabindex="-1"}

The [Fair Housing Act](https://www.hud.gov/program_offices/fair_housing_equal_opp/fair_housing_act_overview) prohibits housing discrimination on the basis of disability, among other things. The act requires landlords to make reasonable modifications to housing units for access purposes. The act also requires new multifamily dwellings to be accessible, and the associated [Fair Housing Accessibility Guidelines](https://www.hud.gov/program_offices/fair_housing_equal_opp/disabilities/fhefhasp) specify those standards.

### The Rehabilitation Act of 1973
{: tabindex="-1"}

According to the Department of Justice (DOJ), "The [Rehabilitation Act](https://www.ada.gov/cguide.htm#anchor65610) prohibits discrimination on the basis of disability in programs conducted by Federal agencies, in programs receiving Federal financial assistance, in Federal employment, and in the employment practices of Federal contractors."

Section 501 of the Rehabilitation (or Rehab) Act requires "affirmative action and nondiscrimination in employment by Federal agencies of the executive branch." Section 503 does the same thing, except with federal contractors.

Section 502 created the United States [Access Board](https://www.access-board.gov/), also known as the Architectural and Transportation Barriers Compliance Board. According to their website, the Access Board "promotes equality for people with disabilities through leadership in accessible design and the development of accessibility guidelines and standards."

Section 504 prohibits federal agencies or programs that receive federal funding from discriminating against persons with disabilities.

Section 508 is actually an amendment to the original law. It was enacted in 1998. Under Section 508, when federal agencies develop, procure, maintain, or use electronic and information technologies, those technologies must be accessible both to employees and members of the public with disabilities.

Section 508 is a law. It's also a standard. For the purposes of following Section 508, the law, what exactly counts as accessible? That's defined by the [Section 508 standards](https://www.access-board.gov/ict/), created by the Access Board. Those standards were "[refreshed](https://www.deque.com/blog/section-508-refresh-news-ict-final-rule-update/)" in 2018 and specifically reference WCAG 2.0 level AA. However, the 508 standards are more comprehensive than WCAG. WCAG stands for the *Web Content* Accessibility Guidelines, and unsurprisingly WCAG was written expressly for the web (although the principles behind WCAG can be extended and applied elsewhere if desired). The 508 standards address more than just web accessibility; they also set standards for meetings and electronic documents like PDFs.

It should be noted: Section 508 sets mandatory ICT accessibility standards for federal agencies. Those standards don't directly apply to the private sector. However, if a private company wants to sell to the federal government, their product will need to conform with the 508 standards. In this way, Section 508 uses the significant buying power of the federal government to push for accessibility outside government. Additionally, private organizations can adopt and follow the Section 508 standards if they wish.

Now we need to talk briefly about VPATs. VPAT stands for [Voluntary Product Accessibility Template](https://www.section508.gov/sell/vpat). A VPAT is a document explaining how well a product or service conforms with the 508 standards. When a federal agency or a private company is procuring a new technology, they might ask the vendor to provide a VPAT, which documents how well that particular product conforms with the 508 standards. VPATs may also document how well a product conforms with WCAG or the EN 301 549 standard. Here's an example: the [VPAT for Canvas](https://www.instructure.com/canvas/accessibility?newhome=canvas), a learning management system used in many schools.

There are two last things I want to note.

First, the General Services Administration (GSA) provides technical support to help federal agencies comply with the law and conform with the standard, and the GSA maintains a [Section 508 website](https://section508.gov) to provide guidance.

Second, technical standards are complex, and not everyone who tests whether a product conforms to the 508 standards may end up with the same result. To address this concern, the [Section 508 ICT Testing Baseline](https://section508coordinators.github.io/ICTTestingBaseline/introduction.html) was developed. The baseline specifies how to test for conformance, so that results are more accurate and consistent. Additionally, the Department of Homeland Security has established the [Trusted Tester](https://www.dhs.gov/trusted-tester) process and certification program to support reliable, repeatable testing that aligns with the baseline.

### The Americans with Disabilities Act
{: tabindex="-1"}

The [Americans with Disabilities Act](https://beta.ada.gov/topics/intro-to-ada/) (ADA) is a broad anti-discrimination act that applies to both public and private sectors. In 2008, the ADA was revised by the ADA Amendments Act, which broadened the law's definition of "disability."

[Title I](https://www.ada.gov/pubs/adastatute08.htm#12112) of the law prohibits employment discrimination. It reads in part: "No covered entity shall discriminate against a qualified individual on the basis of disability in regard to job application procedures, the hiring, advancement, or discharge of employees, employee compensation, job training, and other terms, conditions, and privileges of employment."

[Title II](https://www.ada.gov/pubs/adastatute08.htm#12132) prohibits discrimination by public entities, including public transportation services, school districts, cities, counties, and states. It reads in part: "Subject to the provisions of this subchapter, no qualified individual with a disability shall, by reason of such disability, be excluded from participation in or be denied the benefits of services, programs, or activities of a public entity, or be subjected to discrimination by any such entity."

[Title III](https://www.ada.gov/pubs/adastatute08.htm#12182) prohibits discrimination by places of public accommodations, such as hotels, restaurants, and shops. It reads in part: "No individual shall be discriminated against on the basis of disability in the full and equal enjoyment of the goods, services, facilities, privileges, advantages, or accommodations of any place of public accommodation by any person who owns, leases (or leases to), or operates a place of public accommodation."

Title IV regulates telecommunications.

Private plaintiffs (not the government) can file lawsuits under the ADA, and if they win their case, they can receive injunctive relief. That means, a court can order the defendant to stop discriminating and make a specific change. Successful plaintiffs can also receive attorney's fees to cover the cost of litigation, although they aren't eligible for monetary rewards. However, if the Department of Justice (DOJ) brings a case under the ADA, those who violate the ADA may have to pay anywhere between $55,000 and $150,000 in [monetary penalties](https://www.ada.gov/civil_penalties_2014.htm).

How does the ADA relate to accessibility specifically?

The DOJ has created regulations for the ADA, adopting the [ADA Standards for Accessible Design](https://www.ada.gov/2010ADAstandards_index.htm), which specify accessible standards for physical environments.

Also, the ADA requires covered entities to make reasonable accommodations for persons with disabilities. In employment contexts, a [reasonable accommodation](https://www.dol.gov/agencies/odep/program-areas/employers/accommodations) modifies a job or work environment so that employees with disabilities can still perform essential job functions. In the case of public accommodations, businesses must make reasonable accommodations, modifying their usual way of doing things to serve persons with disabilities. These accommodations often take the form of assistive technologies or accessible physical or digital environments. Additionally, the ADA requires public and private entities to ensure [effective communication](https://adata.org/factsheet/communication) with people with disabilities by providing "auxiliary aids and services" at no additional charge. Again, these "auxiliary aids and services" often take the form of accessible and assistive technologies. The DOJ has also issued [regulations](https://www.ada.gov/effective-comm.htm) clarifying this point.

How does the ADA, and Title III of the ADA in particular, relate to web accessibility in particular? The ADA doesn't directly address web accessibility or create legal standards for ICT accessibility, so to answer that question we need to turn to DOJ rulemaking and case law.

First up, let's look at DOJ rulemaking. Under the Obama administration, the DOJ began the process of developing ADA website guidelines. However, [that rulemaking process stalled](https://www.3playmedia.com/blog/doj-withdraws-ada-website-access-regulations/) under the Trump administration. Nonetheless, even without publishing formal regulations, the DOJ has stated that it believes [the ADA does apply to websites](https://www.adatitleiii.com/2018/10/doj-says-failure-to-comply-with-web-accessibility-guidelines-is-not-necessarily-a-violation-of-the-ada/).

Courts have taken the position that the ADA applies to websites, but there is a circuit split on this question, so the exact details can be somewhat complicated. For now though, I'll point to [Robles v. Dominos Pizza](https://www.adatitleiii.com/2021/06/court-finds-dominos-pizza-violated-the-ada-by-having-an-inaccessible-website-and-orders-wcag-compliance/), a case which sets precedent in the 9th circuit (which includes California). Under this case, websites that have a "nexus" to a physical place of public accommodations are covered under the ADA. The court also issued injunctive relief, ordering Dominos to make its website conform with WCAG 2.0. Additionally, [the judge ruled](https://www.lflegal.com/2021/06/dominos-june-2021/) that “because Defendant’s website violated the ADA, Defendant’s website violates the Unruh Act,” a California state law that we'll talk more about in a moment. Under the Unruh Act, Domino's was ordered to pay $4,000 in monetary damages to the plaintiff.

One last thing to note: the number of lawsuits filed under the ADA has spiked in recent years. [According to UsableNet](https://blog.usablenet.com/2018-ada-web-accessibility-lawsuit-recap-report), ADA web accessibility-related lawsuits grew from 814 in 2017 to 2285 in 2018 --- that's a 181% increase!

If you really want to dive more into the details, check out:

* [The Seyfarth ADA Title III News & Insights Blog](https://www.adatitleiii.com/)
* [Lainey Feingold's website and blog](https://www.lflegal.com/)
* [Ken Nakata's blog posts for Converge Accessibility](https://convergeaccessibility.com/author/ken/)

### Communications and Video Accessibility Act
{: tabindex="-1"}

The [Twenty-First Century Communications and Video Accessibility Act of 2010](https://www.fcc.gov/general/twenty-first-century-communications-and-video-accessibility-act-0) (CVAA) sets accessibility standards for certain communications that are regulated by the Federal Communications Commission (FCC).

Title I of the CVAA focuses on two-way communications like telephones and the Internet. For example, it mandates that some mobile web browsers are accessible to people who are blind or have low vision.

Title II addresses video programming on TV and the Internet. It expands rules for which video programming must include closed captions and audio descriptions, and it also regulates TVs and other equipment so that they better support closed captions and audio descriptions.

You can read more about [the CVAA's requirements ](https://www.fcc.gov/consumers/guides/21st-century-communications-and-video-accessibility-act-cvaa) on the FCC's website.

### Air Carrier Access Act
{: tabindex="-1"}

The [Air Carrier Access Act](https://www.levelaccess.com/accessibility-regulations/air-carrier-access-act/) (ACAA) prohibits commercial airlines from discriminating against people with disabilities. In 2013, the DOJ issued regulations that require airline's websites and kiosks to be accessible to people with disabilities and to conform with WCAG 2.0 level AA in particular.

### Affordable Care Act Section 1557
{: tabindex="-1"}

[Section 1557](https://www.adatitleiii.com/2016/06/new-healthcare-regulations-impose-accessible-technology-requirements/) of the Affordable Care Act, also known as Obamacare, prohibits healthcare organizations from discriminating on the basis of ability, and associated regulations require covered entities to provide "effective communication" and have electronic and information technologies that comply with "modern accessibility standards." The Department of Health and Human Services has encouraged covered entities to conform to WCAG 2.0 level AA to meet this requirement.

### Other Federal Laws
{: tabindex="-1"}

There are other federal laws that have implications for disability rights and accessibility, including the Telecommunications Act, the Architectural Barriers Act, and the Individuals with Disabilities Education Act (IDEA). For more on these laws and others, see "[A Guide to Disability Rights Laws](https://www.ada.gov/cguide.htm)," published by the DOJ's Civil Rights Division.

## State Laws
{: tabindex="-1"}

### California
{: tabindex="-1"}

#### Unruh Civil Rights Act
{: tabindex="-1"}

The [Unruh Civil Rights Act](https://leginfo.legislature.ca.gov/faces/codes_displaySection.xhtml?lawCode=CIV&sectionNum=51) is a broad anti-discrimination law in the state of California, explicitly protecting persons with disabilities. The law applies to businesses in California, and the law explicitly states that:

> A violation of the right of any individual under the federal Americans with Disabilities Act of 1990 (Public Law 101-336) shall also constitute a violation of this section.

That is, ADA violations are also Unruh Act violations. This is of note because "while the ADA authorizes only injunctive relief and attorneys’ fees, California law imposes up to $4,000 [statutory damages](https://www.adatitleiii.com/2014/07/businesses-nationwide-hit-by-wave-of-lawsuits-alleging-inaccessible-websites/) per violation of the law," Minh N. Vu and Kristina M. Launey write. For this reason, ADA lawsuits are often filed in California, where plaintiffs can get this additional money.

Here's one well-known case under the Unruh Act: [Thurston v. Midvale Corp d/b/a Whisper Lounge](https://www.adatitleiii.com/2018/06/ca-court-rules-unruh-act-requires-website-to-conform-to-wcag-2-0-aa-but-denies-damages-for-multiple-visits-to-website/). In this case, Whisper Lounge, a restaurant, had an inaccessible website and was sued by a blind customer. The court ordered Whisper Lounge to pay $4,000 in statutory damages and make its website conform with WCAG 2.0 level AA. For more on the case, see "[California Judge Finds Restaurant’s Inaccessible Website Violated Unruh Act](https://www.levelaccess.com/california-judge-finds-restaurants-inaccessible-website-violated-unruh-act/)" on Level Access' blog.

#### California Consumer Privacy Act
{: tabindex="-1"}

The [California Consumer Privacy Act](https://uxdesign.cc/federal-accessibility-laws-dont-matter-california-s-accessibility-laws-do-7367e32755ca?gi=85811eeb023) (CCPA) went into effect in 2020. It's a privacy law, but it also has important implications for accessibility. Essentially, the CCPA requires that privacy notices be accessible.

For more on this law, see "[The CCPA & Digital Accessibility](https://www.levelaccess.com/the-ccpa-digital-accessibility-overview/)" by Jonathan Avila on Level Access.

### New York
{: tabindex="-1"}

New York is [the top state for digital accessibility lawsuits](https://blog.usablenet.com/a-record-breaking-year-for-ada-digital-accessibility-lawsuits). If an ADA lawsuit is filed in New York, plaintiffs might also allege violations of the New York Human Rights Law and the New York City Human Rights Law, both of which explicitly prohibit discrimination on the basis of disability.

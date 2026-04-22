---
title: DigiTax UAE API Hub
excerpt: >-
  **DigiTax UAE API Hub** contains guides and API reference pages for further
  understanding, equipping you on how to integrate with the UAE FTA System to
  implement PINT AE-compliant e-invoicing.
deprecated: false
hidden: false
metadata:
  robots: index
---
## The DigiTax API for UAE FTA E-Invoicing

<Cards columns={2}>
  <Card title="Navigation" icon="fa-compass">
    If you're new to the DigiTax UAE API Hub, learn how to navigate our pages [here](https://ae.docs.digitax.tech/docs/how-to-use-this-site).
  </Card>

  <Card title="Support" icon="fa-question">
    If you get stuck, or have questions, [email us](mailto:support@namiri.tech) OR\
    Talk to us via the **DigiTax chat** on the bottom right of any page.
  </Card>

  <Card title="FTA integration with DigiTax" icon="fa-bars">
    Explore this page and other detailed guide pages to gain understanding of the FTA System and how DigiTax integration works.
  </Card>

  <Card title="DigiTax UAE API Reference" icon="fa-plug">
    Get the pre-requisites, explore the API endpoints, and learn its feature set via our **interactive API reference** [here](https://ae.docs.digitax.tech/reference).
  </Card>
</Cards>

<Accordion title="DigiTax is Global. Explore other countries here ..." icon="fa-globe">
  You are currently reading a guide in the DigiTax UAE API Hub.

  If you're looking for another country or the general homepage for DigiTax API, navigate to the [DigiTax API homepage](https://docs.digitax.tech), or country-specific API hub pages (ordered alphabetically):

  * <i class="icon-guides" /> **DigiTax UAE API Hub (You are here 🎉)**
  * <i class="icon-guides" /> [DigiTax API Hub Home Page](https://docs.digitax.tech)

  * <i class="icon-guides" /> [DigiTax Kenya API Hub](https://ke.docs.digitax.tech)
  * <i class="icon-guides" /> [DigiTax Nigeria API Hub](https://ng.docs.digitax.tech)
  * <i class="icon-guides" /> [DigiTax Zambia API Hub](https://zm.docs.digitax.tech)
</Accordion>

## Electronic Tax Invoicing in UAE

Countries globally have been opting to digitize their tax systems by imposing e-Invoicing or Electronic Tax Invoicing and Reporting. Electronic Tax Invoicing is a nascent Fintech category globally.

UAE is one of the countries and the country's tax authority/ regulator, **FTA** (Federal Tax Authority) has a transformative e-invoicing system. In this documentation, DigiTax UAE API Hub, we shall simply refer to it as _FTA_.

## Introduction to FTA and DigiTax platform

### FTA

FTA is the tax regulator of the UAE government. It is responsible for the administration of federal taxes in the UAE, including the VAT. FTA e-invoicing is a system that allows businesses to generate and transmit e-invoices to the FTA. FTA e-invoicing is based on the Peppol network.

### Peppol

Peppol is an international network that allows businesses to exchange e-invoices with each other. It is a open standard that is used by businesses all over the world. Peppol is a not-for-profit organization that is committed to the development and promotion of e-invoicing. Learn more about Peppol [here](https://peppol.eu/why-peppol/what-is-peppol/).

> "Peppol is an international framework that sets the standard for cross-border electronic document exchange, including e-invoicing. It enables secure, standardized, and interoperable data sharing between businesses and public sector entities across different countries and IT systems."

### PINT AE

PINT AE are the e-invoicing specifications for the UAE. They are based on the Peppol network, but with some modifications to meet the specific requirements of the UAE. Learn more about PINT AE [here](https://ae.docs.digitax.tech/docs/getting-started-with-pint-ae#pint-ae).

### DigiTax platform

DigiTax platform, by Namiri Technology Services LLC. SOC. (the company), constitutes a suite of digital solutions crafted for effective, simple, and painless tax compliance through **electronic tax invoicing**. These solutions enable taxpayers (individuals and businesses) to generate, digitally sign, and transmit compliant invoices as per the tax authority's (UAE FTA in this case) requirements.

## More about DigiTax

The suite of digital solutions or products under DigiTax, through which one can generate FTA e-invoices, are:

* **DigiTax Dashboard** (Responsive, Web-Browser based, Desktop application)
* **DigiTax API** (for system-to-system integration without the issue of platform hopping), and

DigiTax connects with regional tax authorities/ regulators, so far:

* _**DigiTax UAE**_ integrates you with <Glossary>FTA</Glossary> FTA (Federal Tax Authority System)
* _**DigiTax Nigeria**_ integrates you with <Glossary>NRS</Glossary> NRS (Nigeria Revenue Service)
* _**DigiTax Kenya**_ integrates you with <Glossary>KRA</Glossary> Kenya Revenue Authority
* _**DigiTax Zambia**_ integrates you with <Glossary>ZRA</Glossary> ZRA (Zambia Revenue Authority System)

to offer you a streamlined invoicing system that ensures compliance and supports the growth of your business.

<Image align="center" border={true} caption="DigiTax - Tax Regulators" src="https://files.readme.io/c4b6c503b46201821ae3d228d057ee6db2585be40a27a8607b90ec0d60b733ff-eInvoice.png" />

### DigiTax API Features

The DigiTax API is built with various industry standards for API platforms in mind. Read more on this [here](https://ae.docs.digitax.tech/v1.0/reference/using-the-digitax-UAE-api#digitax-api).

> We invite you to use **DigiTax UAE API** to integrate your system with FTA for automation and to reduce platform-hopping

***

These include:

* RESTful API
* OpenAPI (formerly Swagger): An open-source standard that allows a standardized way to generate, document, and test our APIs.
* Secure authentication with cryptographically signed JWTs (JSON Web Tokens)

To use this API, you'll need access to DigiTax Dashboard environment to get an X-API-Key. Get in touch with [our team](mailto:support@namiri.tech).

These are the steps required to get up and running - [Prerequisites of using DigiTax API](https://ae.docs.digitax.tech/docs/start-using-the-api#/prerequisites)

***

### Guaranteed safety and integrity

We comply with industry and security best practices.

> 👍 DigiTax is built with the best industry practices and to the highest security standards

## DigiTax UAE and FTA e-invoicing system

> **DigiTax UAE** integrates you with FTA e-invoicing system

**DigiTax** is a solution that sits between you; the taxpayer, and the FTA e-invoicing system.

With DigiTax, you gain access to a streamlined invoicing system that ensures compliance and supports your business's growth. Together, DigiTax and FTA e-Invoicing are transforming how businesses in the UAE manage their tax and invoicing obligations.

For us to support individuals and businesses to generate FTA eTIMS invoices, DigiTax is licensed as an FTA approved system integrator.

The speed at which eTIMS invoices are generated is dependent on network capacity, connectivity, and responsiveness of FTA's eTIMS server and the Control Unit transmitting the network traffic.

<Callout icon="🥇" theme="default">
  ### DigiTax is a leading FTA-approved system integrator
</Callout>

## DigiTax UAE API Hub

This API Hub contains guides and API reference pages for further understanding, equipping you on how to integrate with the DigiTax UAE API.

### Explore DigiTax UAE API Guides

Gain understanding of DigiTax UAE integration through our detailed guides.

You're in the guides section of DigiTax UAE API Hub. Explore other pages below to gain context on DigiTax and FTA and understanding of how DigiTax makes it easier for you to integrate your invoicing system with FTA.

### Explore DigiTax UAE API reference

For a great developer experience, the endpoints in the [DigiTax UAE API reference](/reference) are interactive.

Once you're set up in the DigiTax Dashboard, you can generate a Test/ LIVE **X-API-Key** for authorization.

Explore the API endpoints [here](/reference)

***

## Once again, welcome to the DigiTax UAE API Hub

Once again, thank you for reviewing the getting started page of the DigiTax UAE API hub. We're excited you're here! 💚

We invite you to use **DigiTax UAE API** to integrate your system with FTA e-invoicing system for automation and to reduce platform-hopping.

To recap:

* Explore our detailed guides to gain understanding of DigiTax UAE integration. Learn how to navigate them [here](doc:how-to-use-this-site)
* Get the [Prerequisites for using DigiTax UAE API](https://ae.docs.digitax.tech/docs/start-using-the-api#/prerequisites)
* For support, [email us](mailto:support@namiri.tech) OR talk to us via the **DigiTax chat** on the bottom-right of any page

Welcome to the Less Taxing solution - DigiTax.

<Image align="center" width="300px" src="https://files.readme.io/f982859d4fdca89de7d179a31795b159cb6c2e34a9a4dc578b85aba910daf13f-Full-Logo_Slogan_Colour.png" />

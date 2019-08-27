---
title: Programming reference for Windows Driver Kit (WDK)
description: Windows Driver Kit (WDK) 10 is integrated with Microsoft Visual Studio 2017 and Debugging Tools for Windows. This integrated environment gives you the tools you need to develop, build, package, deploy, test, and debug Windows drivers. WDK includes templates for several technologies and driver models, including Windows Driver Frameworks (WDF), Universal Serial Bus (USB), print, networking, and file system filters.
author: tedhudek
ms.assetid: f411c70c-6930-48a1-a8c0-a199d787b84f
ms.date: 10/26/2018
ms.topic: landing-page
ms.prod: windows-hardware
ms.technology: windows-devices
layout: LandingPage
product:
- Windows
---

# Programming reference for Windows Driver Kit (WDK)

Windows Driver Kit (WDK) 10 is integrated with Microsoft Visual Studio 2017 and Debugging Tools for Windows. This integrated environment gives you the tools you need to develop, build, package, deploy, test, and debug Windows drivers. WDK includes templates for several technologies and driver models, including Windows Driver Frameworks (WDF), Universal Serial Bus (USB), print, networking, and file system filters.

<ul class="panelContent cardsFTitle">
    <li>
        <a href="https://visualstudio.microsoft.com/">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="https://docs.microsoft.com/media/logos/logo_vs-ide.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Download Visual Studio IDE</h3>
                        <ul><li><a href="/windows-hardware/drivers/develop/getting-started-with-universal-drivers">Getting Started with Universal Windows drivers</a></li><li><a href="/windows-hardware/drivers/develop/">Developing, Testing, and Deploying Drivers</a></li></ul>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/windows-hardware/drivers/download-the-wdk">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="https://docs.microsoft.com/media/common/i_download-install.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Download the Windows Driver Kit (WDK)</h3>
                            <ul><li><a href="/windows-hardware/drivers/debugger/index">Debugging Tools for Windows</a></li><li><a href="/windows-hardware/drivers/ddi/content/_debugger/index">Debugger API Reference</a></li></ul>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/samples/browse/?products=windows-wdk">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="https://docs.microsoft.com/media/common/i_code-samples.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Windows driver code samples</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>  
</ul>

---

<h2>Driver Reference</h2>

The Windows driver API reference documentation is presented in two different views. When you click on an API, you see a technology-specific table of contents that shows only the APIs pertaining to that technology. When you click on a header, you see a header-specific table of contents that lists all APIs in the selected header.

<ul class="panelContent cardsW">
    <li>
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Driver Model</h3>
                        <p><a href="/windows-hardware/drivers/ddi/content/_wdf/">KMDF and UMDF</a></p><p><a href="/windows-hardware/drivers/ddi/content/_kernel/">Core kernel</a></p>
                    </div>
                </div>
            </div>
        </div>
    </li>
    <li>
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>System</h3>
						<p><a href="/windows-hardware/drivers/ddi/content/_display/">Display</a></p><p><a href="/windows-hardware/drivers/ddi/content/_battery/">Battery</a></p><p><a href="/windows-hardware/drivers/ddi/content/_acpi/">ACPI</a></p><p><a href="/windows-hardware/drivers/ddi/content/_storage/">Storage</a></p><p><a href="/windows-hardware/drivers/ddi/content/_ifsk/">File system</a></p><p><a href="/windows-hardware/drivers/ddi/content/_gpiobtn/">Hardware notifications</a></p><p><a href="/windows-hardware/drivers/ddi/content/_powermeter/">Power metering</a></p><p><a href="/windows-hardware/drivers/ddi/content/_biometric/">Biometric</a></p>
                     </div>
                </div>
            </div>
        </div>
    </li>
    <li>
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Devices</h3>
                        <p><a href="/windows-hardware/drivers/ddi/content/_print/">Print</a></p><p><a                            href="/windows-hardware/drivers/ddi/content/_hid/">HID</a></p><p><a                                    href="/windows-hardware/drivers/ddi/content/_sensors/">Sensors</a></p><p><a                            href="/windows-hardware/drivers/ddi/content/_pos/">Point of service</a></p><p><a                       href="/windows-hardware/drivers/ddi/content/_image/">Image and Scan</a></p>
                    </div>
                </div>
            </div>
        </div>
    </li>
    <li>
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Connectivity </h3>
                        <p><a href="/windows-hardware/drivers/ddi/content/_netvista/">Network</a></p><p><a href="/windows-hardware/drivers/ddi/content/_bltooth/">Bluetooth</a></p><p><a href="/windows-hardware/drivers/ddi/content/_nfpdrivers/">NFC</a></p><p><a href="/windows-hardware/drivers/ddi/content/_smartcrd/">Smart Card Readers</a></p>
                    </div>
                </div>
            </div>
        </div>
    </li>
    <li>
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Streaming</h3>
                        <p><a href="/windows-hardware/drivers/ddi/content/_audio/">Audio</a></p><p><a                          href="/windows-hardware/drivers/ddi/content/_stream/">Camera</a></p>
                    </div>
                </div>
            </div>
        </div>
    </li>
    <li>
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Buses and ports</h3>
                        <p><a href="/windows-hardware/drivers/ddi/content/_usbref/">USB</a></p><p><a                             href="/windows-hardware/drivers/ddi/content/_spb/">I2C, SPI</a></p><p><a                               href="/windows-hardware/drivers/ddi/content/_pci/">PCI</a></p><p><a                                    href="/windows-hardware/drivers/ddi/content/_gpio/">GPIO</a></p>
                    </div>
                </div>
            </div>
        </div>
    </li>
</ul>
  
---

<h2>Related</h2>
<ul class="panelContent cardsW">
    <li>
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Resources</h3>
                        <p><a href="/windows-hardware/drivers/what-s-new-in-driver-development">What's new in driver development</a></p><p><a href="/windows-hardware/drivers/gettingstarted/concepts-and-knowledge-for-all-driver-developers">Concepts for all driver developers</a></p><p><a href="/windows-hardware/drivers/">Developing, Testing, and Deploying Drivers</a></p><p><a href="https://developer.microsoft.com/windows/hardware">Windows Driver Frameworks</a></p><p><a href="/windows-hardware/drivers/device-and-driver-technologies">Device and Driver Technologies </a></p><p><a href="/windows-hardware/drivers/install/">Device and Driver Installation</a></p><p><a href="https://docs.microsoft.com/windows-hardware/drivers/">Kernel-Mode Driver Architecture</a></p><p><a href="https://docs.microsoft.com/windows-hardware/drivers/">Device and Driver Development Tools</a></p>
                    </div>
                </div>
            </div>
        </div>
    </li>
 </uL>   

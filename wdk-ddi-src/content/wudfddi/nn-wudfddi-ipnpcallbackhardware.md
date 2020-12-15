---
UID: NN:wudfddi.IPnpCallbackHardware
title: IPnpCallbackHardware (wudfddi.h)
description: The IPnpCallbackHardware interface is a Plug and Play (PnP) and power management (PM) interface.
old-location: wdf\ipnpcallbackhardware.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IPnpCallbackHardware interface"]
ms.keywords: IPnpCallbackHardware, IPnpCallbackHardware interface, IPnpCallbackHardware interface,described, UMDFDeviceObjectRef_4b39ad3c-6fa6-4c47-aba8-676a6f628f1b.xml, umdf.ipnpcallbackhardware, wdf.ipnpcallbackhardware, wudfddi/IPnpCallbackHardware
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IPnpCallbackHardware
 - wudfddi/IPnpCallbackHardware
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IPnpCallbackHardware
---

# IPnpCallbackHardware interface


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IPnpCallbackHardware</b> interface is a Plug and Play (PnP) and power management (PM) interface.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPnpCallbackHardware</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPnpCallbackHardware</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks

A driver registers the <b>IPnpCallbackHardware</b> interface when the driver calls the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackhardware2">IPnpCallbackHardware2</a>

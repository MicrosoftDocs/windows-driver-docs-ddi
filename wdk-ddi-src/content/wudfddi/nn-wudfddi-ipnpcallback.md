---
UID: NN:wudfddi.IPnpCallback
title: IPnpCallback (wudfddi.h)
description: The IPnpCallback interface is a Plug and Play (PnP) and power management (PM) interface.
old-location: wdf\ipnpcallback.htm
tech.root: wdf
ms.assetid: b6ab28e1-08d5-49ee-931a-8e2fe68bd75e
ms.date: 02/26/2018
keywords: ["IPnpCallback interface"]
ms.keywords: IPnpCallback, IPnpCallback interface, IPnpCallback interface,described, UMDFDeviceObjectRef_1e101e13-802b-4196-a76c-ed4103d6fbe3.xml, umdf.ipnpcallback, wdf.ipnpcallback, wudfddi/IPnpCallback
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
 - IPnpCallback
 - wudfddi/IPnpCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IPnpCallback
---

# IPnpCallback interface


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IPnpCallback</b> interface is a Plug and Play (PnP) and power management (PM) interface.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPnpCallback</b> interface inherits from the <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPnpCallback</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks

A driver registers the <b>IPnpCallback</b> interface when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object.


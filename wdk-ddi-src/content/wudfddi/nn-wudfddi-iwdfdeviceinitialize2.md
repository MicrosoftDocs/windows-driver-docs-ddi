---
UID: NN:wudfddi.IWDFDeviceInitialize2
title: IWDFDeviceInitialize2 (wudfddi.h)
description: The IWDFDeviceInitialize2 interface is a helper interface that allows a driver to specify a preferred buffer retrieval mode and buffer access method.
old-location: wdf\iwdfdeviceinitialize2.htm
tech.root: wdf
ms.assetid: 78d0c888-955f-481f-aa59-f2e5eea1aa81
ms.date: 02/26/2018
keywords: ["IWDFDeviceInitialize2 interface"]
ms.keywords: IWDFDeviceInitialize2, IWDFDeviceInitialize2 interface, IWDFDeviceInitialize2 interface,described, UMDFDeviceObjectRef_0a7dcdea-43e7-4a0a-b55c-34d18eca65e8.xml, umdf.iwdfdeviceinitialize2, wdf.iwdfdeviceinitialize2, wudfddi/IWDFDeviceInitialize2
f1_keywords:
 - "wudfddi/IWDFDeviceInitialize2"
 - "IWDFDeviceInitialize2"
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFDeviceInitialize2
targetos: Windows
req.typenames: 
---

# IWDFDeviceInitialize2 interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFDeviceInitialize2</b> interface is a helper interface that allows a driver to specify a preferred buffer retrieval mode and buffer access method.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFDeviceInitialize2</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdeviceinitialize">IWDFDeviceInitialize</a>. <b>IWDFDeviceInitialize2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks



Drivers obtain the <b>IWDFDeviceInitialize2</b> interface by calling <b>IWDFDeviceInitialize::QueryInterface</b>.




---
UID: NN:wudfddi.IWDFDevice
title: IWDFDevice (wudfddi.h)
description: The IWDFDevice interface exposes a device object, which is a representation of a device on the system.
old-location: wdf\iwdfdevice.htm
tech.root: wdf
ms.assetid: b0f8a156-e0e0-48d1-9e23-4ac07795df07
ms.date: 02/26/2018
keywords: ["IWDFDevice interface"]
ms.keywords: IWDFDevice, IWDFDevice interface, IWDFDevice interface,described, UMDFDeviceObjectRef_d0dc8041-1d51-457b-8632-e500bf4df724.xml, umdf.iwdfdevice, wdf.iwdfdevice, wudfddi/IWDFDevice
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFDevice
 - wudfddi/IWDFDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDevice
---

# IWDFDevice interface


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFDevice</b> interface exposes a device object, which is a representation of a device on the system.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFDevice</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>. <b>IWDFDevice</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks

Each device object has a parent driver object. When a new device arrives in the system, the framework calls the parent driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-idriverentry-ondeviceadd">IDriverEntry::OnDeviceAdd</a> callback function to notify the driver about the arrival. The driver can then call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to receive a pointer to the <b>IWDFDevice</b> interface for the new device object.


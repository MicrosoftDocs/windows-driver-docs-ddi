---
UID: NN:wudfddi.IWDFDeviceInitialize
title: IWDFDeviceInitialize (wudfddi.h)
description: The IWDFDeviceInitialize interface is a helper interface that the framework supplies as an input parameter to the driver's IDriverEntry::OnDeviceAdd method.
old-location: wdf\iwdfdeviceinitialize.htm
tech.root: wdf
ms.assetid: a776069c-0cbb-4ae9-bf6b-1d300dbcec34
ms.date: 02/26/2018
keywords: ["IWDFDeviceInitialize interface"]
ms.keywords: IWDFDeviceInitialize, IWDFDeviceInitialize interface, IWDFDeviceInitialize interface,described, UMDFDeviceObjectRef_b63038ef-0e6e-4417-96de-0c3f5ec1866e.xml, umdf.iwdfdeviceinitialize, wdf.iwdfdeviceinitialize, wudfddi/IWDFDeviceInitialize
f1_keywords:
 - "wudfddi/IWDFDeviceInitialize"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFDeviceInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDeviceInitialize interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFDeviceInitialize</b> interface is a helper interface that the framework supplies as an input parameter to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-idriverentry-ondeviceadd">IDriverEntry::OnDeviceAdd</a> method.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFDeviceInitialize</b> interface inherits from the <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IWDFDeviceInitialize</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks



 The driver calls the methods of this interface to set the properties for a new device object and passes this interface as an input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create the new device object.

Do not use  this interface after calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>.




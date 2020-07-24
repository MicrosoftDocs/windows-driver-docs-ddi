---
UID: NF:wudfddi.IPnpCallbackHardware2.OnReleaseHardware
title: IPnpCallbackHardware2::OnReleaseHardware (wudfddi.h)
description: The OnReleaseHardware method performs operations that are needed when a device is no longer accessible.
old-location: wdf\ipnpcallbackhardware2_onreleasehardware.htm
tech.root: wdf
ms.assetid: 652B92C2-EF04-482A-BB57-9F64F947EE4F
ms.date: 02/26/2018
keywords: ["IPnpCallbackHardware2::OnReleaseHardware"]
ms.keywords: IPnpCallbackHardware2 interface,OnReleaseHardware method, IPnpCallbackHardware2.OnReleaseHardware, IPnpCallbackHardware2::OnReleaseHardware, OnReleaseHardware, OnReleaseHardware method, OnReleaseHardware method,IPnpCallbackHardware2 interface, umdf.ipnpcallbackhardware2_onreleasehardware, wdf.ipnpcallbackhardware2_onreleasehardware, wudfddi/IPnpCallbackHardware2::OnReleaseHardware
f1_keywords:
 - "wudfddi/IPnpCallbackHardware2.OnReleaseHardware"
 - "IPnpCallbackHardware2.OnReleaseHardware"
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IPnpCallbackHardware2.OnReleaseHardware
targetos: Windows
req.typenames: 
---

# IPnpCallbackHardware2::OnReleaseHardware


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnReleaseHardware</b> method performs operations that are needed when a device is no longer accessible.


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a> interface for the framework device object.


### -param pWdfResourcesTranslated [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfcmresourcelist">IWDFCmResourceList</a> interface for the framework resource-list object that identifies the translated hardware resources that the Plug and Play manager has assigned to the device.


## -returns



<b>OnReleaseHardware</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h. Do not return HRESULT_FROM_NT(STATUS_NOT_SUPPORTED).




## -remarks



A driver registers the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackhardware2">IPnpCallbackHardware2</a> interface when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object.

 
The <b>OnReleaseHardware</b> method must free resources that were allocated during the call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onpreparehardware">IPnpCallbackHardware2::OnPrepareHardware</a> method, regardless of whether <b>OnPrepareHardware</b> succeeded or failed. As such, <b>OnReleaseHardware</b> must be able to handle the cleanup of partial resources.

For information about deleting an interrupt object, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/deleting-an-interrupt-object">Deleting an Interrupt Object</a>.

For information about parsing hardware resources, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/finding-and-mapping-hardware-resources-in-umdf-1-x-drivers">Finding and Mapping Hardware Resources in a UMDF Driver</a>.



#### Examples

See example code in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-mapiospace">IWDFDevice3::MapIoSpace</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackhardware2">IPnpCallbackHardware2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onpreparehardware">OnPrepareHardware</a>
 

 


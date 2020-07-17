---
UID: NF:wudfddi.IPnpCallbackHardware2.OnPrepareHardware
title: IPnpCallbackHardware2::OnPrepareHardware (wudfddi.h)
description: The OnPrepareHardware method performs any operations that are needed to make a device accessible to the driver.
old-location: wdf\ipnpcallbackhardware2_onpreparehardware.htm
tech.root: wdf
ms.assetid: 830D706A-016C-4637-829F-2014AD1A1309
ms.date: 02/26/2018
keywords: ["IPnpCallbackHardware2::OnPrepareHardware"]
ms.keywords: IPnpCallbackHardware2 interface,OnPrepareHardware method, IPnpCallbackHardware2.OnPrepareHardware, IPnpCallbackHardware2::OnPrepareHardware, OnPrepareHardware, OnPrepareHardware method, OnPrepareHardware method,IPnpCallbackHardware2 interface, umdf.ipnpcallbackhardware2_onpreparehardware, wdf.ipnpcallbackhardware2_onpreparehardware, wudfddi/IPnpCallbackHardware2::OnPrepareHardware
f1_keywords:
 - "wudfddi/IPnpCallbackHardware2.OnPrepareHardware"
 - "IPnpCallbackHardware2.OnPrepareHardware"
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
- IPnpCallbackHardware2.OnPrepareHardware
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPnpCallbackHardware2::OnPrepareHardware


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


   The <b>OnPrepareHardware</b> method performs any operations that are needed to make a device accessible to the driver.
  


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a> interface for the framework device object.


### -param pWdfResourcesRaw [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfcmresourcelist">IWDFCmResourceList</a> interface for the framework resource-list object that identifies the raw hardware resources that the Plug and Play manager has assigned to the device.


### -param pWdfResourcesTranslated [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfcmresourcelist">IWDFCmResourceList</a> interface for the framework resource-list object that identifies the translated hardware resources that the Plug and Play manager has assigned to the device.


## -returns



<b>OnPrepareHardware</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h. Do not return HRESULT_FROM_NT(STATUS_NOT_SUPPORTED).

If <b>OnPrepareHardware</b> returns an error code, the framework will still call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onreleasehardware">IPnpCallbackHardware2::OnReleaseHardware</a> method. The <b>OnReleaseHardware</b> method can then free resources that were allocated during the call to <b>OnPrepareHardware</b>. Because <b>OnReleaseHardware</b> must free resources for both success and failure cases of <b>OnPrepareHardware</b>, <b>OnReleaseHardware</b> must be able to handle the cleanup of partial resources.




## -remarks



The <b>IPnpCallbackHardware2::OnPrepareHardware</b> method differs from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware-onpreparehardware">IPnpCallbackHardware::OnPrepareHardware</a> method in that it receives raw and translated resources.

For information about parsing hardware resources, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/finding-and-mapping-hardware-resources-in-umdf-1-x-drivers">Finding and Mapping Hardware Resources in a UMDF Driver</a>.



#### Examples

See example code in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-mapiospace">IWDFDevice3::MapIoSpace</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackhardware2">IPnpCallbackHardware2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onreleasehardware">OnReleaseHardware</a>
 

 


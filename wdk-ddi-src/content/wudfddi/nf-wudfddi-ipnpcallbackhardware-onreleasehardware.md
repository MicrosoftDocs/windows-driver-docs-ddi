---
UID: NF:wudfddi.IPnpCallbackHardware.OnReleaseHardware
title: IPnpCallbackHardware::OnReleaseHardware (wudfddi.h)
description: The OnReleaseHardware method notifies a driver to perform operations that are necessary when the specified hardware is no longer accessible.
old-location: wdf\ipnpcallbackhardware_onreleasehardware.htm
tech.root: wdf
ms.assetid: 8975941a-21ad-4d51-9215-b35fa65cdfeb
ms.date: 02/26/2018
keywords: ["IPnpCallbackHardware::OnReleaseHardware"]
ms.keywords: IPnpCallbackHardware interface,OnReleaseHardware method, IPnpCallbackHardware.OnReleaseHardware, IPnpCallbackHardware::OnReleaseHardware, OnReleaseHardware, OnReleaseHardware method, OnReleaseHardware method,IPnpCallbackHardware interface, UMDFDeviceObjectRef_d8966916-01c2-4e3d-b69b-d97ac06fe48a.xml, umdf.ipnpcallbackhardware_onreleasehardware, wdf.ipnpcallbackhardware_onreleasehardware, wudfddi/IPnpCallbackHardware::OnReleaseHardware
f1_keywords:
 - "wudfddi/IPnpCallbackHardware.OnReleaseHardware"
 - "IPnpCallbackHardware.OnReleaseHardware"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IPnpCallbackHardware.OnReleaseHardware
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPnpCallbackHardware::OnReleaseHardware


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnReleaseHardware</b> method notifies a driver to perform operations that are necessary when the specified hardware is no longer accessible.


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a> interface for the device object of the device that is no longer accessible.


## -returns



<b>OnReleaseHardware</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h. Do not return HRESULT_FROM_NT(STATUS_NOT_SUPPORTED).

This method must use the HRESULT_FROM_NT macro to return a specific HRESULT value to  return status to a kernel-mode client. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-1-x-drivers">Supporting Kernel-mode Clients</a>.




## -remarks



A driver registers the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackhardware">IPnpCallbackHardware</a> interface when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object. 

The <b>OnReleaseHardware</b> method must free resources that were allocated during the call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware-onpreparehardware">IPnpCallbackHardware::OnPrepareHardware</a> method whether <b>OnPrepareHardware</b> succeeded or failed. Therefore, <b>OnReleaseHardware</b> must be able to handle the cleanup of partial resources.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/finding-and-mapping-hardware-resources-in-umdf-1-x-drivers">Finding and Mapping Hardware Resources in a UMDF Driver</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackhardware">IPnpCallbackHardware</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onreleasehardware">IPnpCallbackHardware2::OnReleaseHardware</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware-onpreparehardware">IPnpCallbackHardware::OnPrepareHardware</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>
 

 


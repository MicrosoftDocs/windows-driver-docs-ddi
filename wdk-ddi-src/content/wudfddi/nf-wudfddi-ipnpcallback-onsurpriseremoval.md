---
UID: NF:wudfddi.IPnpCallback.OnSurpriseRemoval
title: IPnpCallback::OnSurpriseRemoval (wudfddi.h)
description: The OnSurpriseRemoval method notifies a driver after a device is removed from a computer unexpectedly so that the driver can perform necessary operations.
old-location: wdf\ipnpcallback_onsurpriseremoval.htm
tech.root: wdf
ms.assetid: 4289406f-dda0-4439-be6e-6e638bb46e1f
ms.date: 02/26/2018
keywords: ["IPnpCallback::OnSurpriseRemoval"]
ms.keywords: IPnpCallback interface,OnSurpriseRemoval method, IPnpCallback.OnSurpriseRemoval, IPnpCallback::OnSurpriseRemoval, OnSurpriseRemoval, OnSurpriseRemoval method, OnSurpriseRemoval method,IPnpCallback interface, UMDFDeviceObjectRef_92f0661b-48a5-4d85-9bcf-f763c38b08ed.xml, umdf.ipnpcallback_onsurpriseremoval, wdf.ipnpcallback_onsurpriseremoval, wudfddi/IPnpCallback::OnSurpriseRemoval
f1_keywords:
 - "wudfddi/IPnpCallback.OnSurpriseRemoval"
 - "IPnpCallback.OnSurpriseRemoval"
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
- IPnpCallback.OnSurpriseRemoval
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPnpCallback::OnSurpriseRemoval


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnSurpriseRemoval</b> method notifies a driver after a device is removed from a computer unexpectedly so that the driver can perform necessary operations.


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a> interface for the device object of the device that is removed unexpectedly.


## -remarks



A driver registers the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallback">IPnpCallback</a> interface when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object. 

The framework does not synchronize the <b>OnSurpriseRemoval</b> callback function with other PnP and power management callback functions.  

For more information about when the framework calls this callback function, and for more information about synchronization issues, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/a-user-unplugs-a-device">A User Unplugs a Device</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallback">IPnpCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>
 

 


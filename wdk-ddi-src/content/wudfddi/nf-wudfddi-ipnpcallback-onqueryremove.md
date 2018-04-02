---
UID: NF:wudfddi.IPnpCallback.OnQueryRemove
title: IPnpCallback::OnQueryRemove method
author: windows-driver-content
description: The OnQueryRemove method notifies a driver before a device is removed from a computer.
old-location: wdf\ipnpcallback_onqueryremove.htm
old-project: wdf
ms.assetid: ae95a22d-7b5b-4854-b2f5-76b46cf268f9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPnpCallback, IPnpCallback interface, OnQueryRemove method, IPnpCallback::OnQueryRemove, OnQueryRemove method, OnQueryRemove method, IPnpCallback interface, OnQueryRemove,IPnpCallback.OnQueryRemove, UMDFDeviceObjectRef_27404593-38b6-46cc-8dcc-809d159822b6.xml, umdf.ipnpcallback_onqueryremove, wdf.ipnpcallback_onqueryremove, wudfddi/IPnpCallback::OnQueryRemove
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IPnpCallback.OnQueryRemove
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IPnpCallback::OnQueryRemove method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnQueryRemove</b> method notifies a driver before a device is removed from a computer. 


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a> interface for the device object of the device that will be removed.


## -returns



If the driver determines that the device can be stopped and removed, the <b>OnQueryRemove</b> callback method must return S_OK or another status code for which SUCCEEDED(status) equals <b>TRUE</b>. Otherwise, it must return a status code for which SUCCEEDED(status) equals <b>FALSE</b>.   HRESULT error codes are defined in Winerror.h. Do not return HRESULT_FROM_NT(STATUS_NOT_SUPPORTED).

This method must use the HRESULT_FROM_NT macro to return a specific HRESULT value to  return status to a kernel-mode client. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-1-x-drivers">Supporting Kernel-mode Clients</a>.




## -remarks



A driver registers the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556762">IPnpCallback</a> interface when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object. 

The framework does not synchronize the <b>OnQueryRemove</b> callback function with other PnP and power management callback functions.  

For more information about the <b>OnQueryRemove</b> callback method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/a-user-unplugs-a-device">A User Unplugs a Device</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556762">IPnpCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>
 

 


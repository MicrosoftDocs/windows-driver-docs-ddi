---
UID: NF:wudfddi.IPnpCallback.OnSurpriseRemoval
title: IPnpCallback::OnSurpriseRemoval method
author: windows-driver-content
description: The OnSurpriseRemoval method notifies a driver after a device is removed from a computer unexpectedly so that the driver can perform necessary operations.
old-location: wdf\ipnpcallback_onsurpriseremoval.htm
old-project: wdf
ms.assetid: 4289406f-dda0-4439-be6e-6e638bb46e1f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPnpCallback, IPnpCallback interface, OnSurpriseRemoval method, IPnpCallback::OnSurpriseRemoval, OnSurpriseRemoval method, OnSurpriseRemoval method, IPnpCallback interface, OnSurpriseRemoval,IPnpCallback.OnSurpriseRemoval, UMDFDeviceObjectRef_92f0661b-48a5-4d85-9bcf-f763c38b08ed.xml, umdf.ipnpcallback_onsurpriseremoval, wdf.ipnpcallback_onsurpriseremoval, wudfddi/IPnpCallback::OnSurpriseRemoval
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
req.lib: wudfddi.h
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
-	IPnpCallback.OnSurpriseRemoval
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IPnpCallback::OnSurpriseRemoval method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnSurpriseRemoval</b> method notifies a driver after a device is removed from a computer unexpectedly so that the driver can perform necessary operations.


## -syntax


````
void OnSurpriseRemoval(
  [in] IWDFDevice *pWdfDevice
);
````


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface for the device object of the device that is removed unexpectedly.


## -returns



None




## -remarks



A driver registers the <a href="..\wudfddi\nn-wudfddi-ipnpcallback.md">IPnpCallback</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object. 

The framework does not synchronize the <b>OnSurpriseRemoval</b> callback function with other PnP and power management callback functions.  

For more information about when the framework calls this callback function, and for more information about synchronization issues, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/a-user-unplugs-a-device">A User Unplugs a Device</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>



<a href="..\wudfddi\nn-wudfddi-ipnpcallback.md">IPnpCallback</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPnpCallback::OnSurpriseRemoval method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NF:wudfddi.IPnpCallback.OnD0Entry
title: IPnpCallback::OnD0Entry method
author: windows-driver-content
description: The OnD0Entry method notifies a driver when a device enters the D0 power state so that the driver can perform necessary operations, such as enabling the device.
old-location: wdf\ipnpcallback_ond0entry.htm
old-project: wdf
ms.assetid: 6efa3d8e-3e54-4ab1-82e0-08ba12bb1877
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: OnD0Entry, wdf.ipnpcallback_ond0entry, OnD0Entry method, IPnpCallback interface, OnD0Entry method, UMDFDeviceObjectRef_96da33eb-c6ef-41f0-9a4c-1a8e8158d023.xml, OnD0Entry method, IPnpCallback interface, IPnpCallback::OnD0Entry, IPnpCallback, wudfddi/IPnpCallback::OnD0Entry, umdf.ipnpcallback_ond0entry
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Wudfddi.h
apiname:
-	IPnpCallback.OnD0Entry
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IPnpCallback::OnD0Entry method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnD0Entry</b> method notifies a driver when a device enters the D0 power state so that the driver can perform necessary operations, such as enabling the device. 


## -syntax


````
HRESULT OnD0Entry(
  [in] IWDFDevice             *pWdfDevice,
  [in] WDF_POWER_DEVICE_STATE previousState
);
````


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface for the device object of the device that enters the D0 power state.


### -param previousState [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_power_device_state.md">WDF_POWER_DEVICE_STATE</a>-typed value that identifies the power state of the device before it entered the D0 power state.


## -returns



If the <b>OnD0Entry</b> callback encounters no errors, it must return
       S_OK or another status code for which SUCCEEDED(status) equals <b>TRUE</b>.

 If it returns a status code for which SUCCEEDED(status) equals <b>FALSE</b>, the framework removes the device. If the device's drivers are not supporting other devices on the system, the I/O manager unloads the drivers. 
The framework notifies the PnP manager, which then attempts to restart the device by requesting the bus driver to reenumerate its devices. If your driver was unloaded, it will be reloaded.    In this case, the framework will not call the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556803">IPnpCallback::OnD0Exit</a> callback function.

HRESULT error codes are defined in Winerror.h. 




## -remarks



A driver registers the <a href="..\wudfddi\nn-wudfddi-ipnpcallback.md">IPnpCallback</a> interface when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>



<a href="..\wudfddi\nn-wudfddi-ipnpcallback.md">IPnpCallback</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>



<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_power_device_state.md">WDF_POWER_DEVICE_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPnpCallback::OnD0Entry method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


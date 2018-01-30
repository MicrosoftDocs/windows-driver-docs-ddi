---
UID: NF:wudfddi.IWDFDevice2.GetDeviceStackIoTypePreference
title: IWDFDevice2::GetDeviceStackIoTypePreference method
author: windows-driver-content
description: The GetDeviceStackIoTypePreference method retrieves the buffer access methods that the framework is using for a device.
old-location: wdf\iwdfdevice2_getdevicestackiotypepreference.htm
old-project: wdf
ms.assetid: 3a1f6432-3f61-4502-ac98-fa984539f88e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: GetDeviceStackIoTypePreference method, IWDFDevice2 interface, GetDeviceStackIoTypePreference, wudfddi/IWDFDevice2::GetDeviceStackIoTypePreference, IWDFDevice2 interface, GetDeviceStackIoTypePreference method, GetDeviceStackIoTypePreference method, IWDFDevice2::GetDeviceStackIoTypePreference, wdf.iwdfdevice2_getdevicestackiotypepreference, umdf.iwdfdevice2_getdevicestackiotypepreference, IWDFDevice2, UMDFDeviceObjectRef_f6402826-fe3b-46c7-a4a8-d1d4f74e4b5c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFDevice2.GetDeviceStackIoTypePreference
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFDevice2::GetDeviceStackIoTypePreference method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDeviceStackIoTypePreference</b> method retrieves the buffer access methods that the framework is using for a device.


## -syntax


````
void GetDeviceStackIoTypePreference(
  [out] WDF_DEVICE_IO_TYPE *ReadWritePreference,
  [out] WDF_DEVICE_IO_TYPE *IoControlPreference
);
````


## -parameters




### -param ReadWritePreference [out]

A pointer to a driver-allocated location that receives a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>-typed value. This value identifies the buffer access method that the framework is using for a device's read and write requests.


### -param IoControlPreference [out]

A pointer to a driver-allocated location that receives a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE</a>-typed value. This value that identifies the buffer access method that the framework is using for a device's I/O control requests.


## -returns


None.



## -remarks


If your driver calls <b>GetDeviceStackIoTypePreference</b> before the PnP manager has loaded all of the device's drivers, the values that <b>GetDeviceStackIoTypePreference</b> retrieves might not be the values that it actually uses.

For more information about how the framework chooses a buffer access method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">How UMDF Chooses a Buffer Access Method for an I/O Request</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556969">IWDFDeviceInitialize2::SetIoTypePreference</a>

<a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice2::GetDeviceStackIoTypePreference method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


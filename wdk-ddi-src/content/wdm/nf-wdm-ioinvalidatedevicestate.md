---
UID: NF:wdm.IoInvalidateDeviceState
title: IoInvalidateDeviceState function
author: windows-driver-content
description: The IoInvalidateDeviceState routine notifies the PnP manager that some aspect of the PnP state of a device has changed.
old-location: kernel\ioinvalidatedevicestate.htm
old-project: kernel
ms.assetid: ca27e8d3-80ee-467c-9c88-19770cd86d94
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , D, I, IoInvalidateDeviceState, IoInvalidateDeviceState routine [Kernel-Mode Driver Architecture], S, a, c, d, e, i, k104_05ef79e6-a7d1-4de4-aefa-5aa7d9121f04.xml, kernel.ioinvalidatedevicestate, l, n, o, t, v, wdm/IoInvalidateDeviceState"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoInvalidateDeviceState
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoInvalidateDeviceState function


## -description


The <b>IoInvalidateDeviceState</b> routine notifies the PnP manager that some aspect of the PnP state of a device has changed. 


## -syntax


````
VOID IoInvalidateDeviceState(
  _In_ PDEVICE_OBJECT PhysicalDeviceObject
);
````


## -parameters




### -param PhysicalDeviceObject [in]

Pointer to the PDO for the device. 


## -returns



None




## -remarks



Drivers call this routine to indicate that something has changed with respect to one of the following aspects of a device's PnP state:

PNP_DEVICE_DISABLED

PNP_DEVICE_DONT_DISPLAY_IN_UI

PNP_DEVICE_FAILED

PNP_DEVICE_NOT_DISABLEABLE

PNP_DEVICE_REMOVED

PNP_DEVICE_RESOURCE_REQUIREMENTS_CHANGED

For descriptions of the preceding constants, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559618">PNP_DEVICE_STATE</a>.

In response to this routine, the PnP manager sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551698">IRP_MN_QUERY_PNP_DEVICE_STATE</a> request to the device stack, to determine the current PnP state of the device.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551698">IRP_MN_QUERY_PNP_DEVICE_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559618">PNP_DEVICE_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoInvalidateDeviceState routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


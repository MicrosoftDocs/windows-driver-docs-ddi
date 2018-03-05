---
UID: NF:hwnclx.HwNProcessAddDevicePostDeviceCreate
title: HwNProcessAddDevicePostDeviceCreate function
author: windows-driver-content
description: Creates I/O queues. It should be called after the client driver’s EVT_WDF_DRIVER_DEVICE_ADD callback function is invoked and the device object has been created.
old-location: gpiobtn\hwnprocessadddevicepostdevicecreate.htm
old-project: gpiobtn
ms.assetid: 907cdeac-e2f0-48fa-bbf0-082c0fce6401
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: HwNProcessAddDevicePostDeviceCreate, HwNProcessAddDevicePostDeviceCreate function, gpiobtn.hwnprocessadddevicepostdevicecreate, hwnclx/HwNProcessAddDevicePostDeviceCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hwnclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Mshwnclxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Mshwnclxstub.lib
-	Mshwnclxstub.dll
api_name:
-	HwNProcessAddDevicePostDeviceCreate
product: Windows
targetos: Windows
req.typenames: HWN_CLX_EXPORT_INDEX, *PHWN_CLX_EXPORT_INDEX
---

# HwNProcessAddDevicePostDeviceCreate function


## -description



			
             Creates I/O queues. It should be called after the client driver’s <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EVT_WDF_DRIVER_DEVICE_ADD</a> callback function is invoked and the device object has been created. 


## -syntax


````
FORCEINLINE NTSTATUS  HwNProcessAddDevicePostDeviceCreate(
  _In_ WDFDRIVER  Driver,
  _In_ WDFDEVICE  Device,
  _In_ LPGUID     DeviceGuid
);
````


## -parameters




### -param Driver [in]

Handle to the client drivers framework driver object. 


### -param Device [in]

Handle to the framework device object. 


### -param DeviceGuid [in]

Pointer to the GUID for the client driver. Valid values are defined in Hwn.h, which ships with Window SDK.


## -returns



Returns STATUS_SUCCESS if function succeeds. Returns STATUS_INVALID_PARAMETER if corresponding client driver can't be found. Otherwise, it returns one of the error status values defined in Ntstatus.h.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn789335">Hardware notifications support</a>



<a href="https://msdn.microsoft.com/405ff6db-9bc0-42f3-a740-49dd3967a8b3">Hardware notifications reference</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [gpiobtn\gpiobtn]:%20HwNProcessAddDevicePostDeviceCreate function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


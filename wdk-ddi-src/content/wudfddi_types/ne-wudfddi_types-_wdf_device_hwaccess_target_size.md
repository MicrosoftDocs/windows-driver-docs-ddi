---
UID: NE:wudfddi_types._WDF_DEVICE_HWACCESS_TARGET_SIZE
title: "_WDF_DEVICE_HWACCESS_TARGET_SIZE"
author: windows-driver-content
description: The WDF_DEVICE_HWACCESS_TARGET_SIZE enumeration is used internally by the framework. Do not use.
old-location: wdf\wdf_device_hwaccess_target_size.htm
old-project: wdf
ms.assetid: C675431E-6213-4FA8-86DB-65FE6EE90853
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfdevice/WdfDeviceHwAccessTargetSizeUlong64, wudfddi_types/WdfDeviceHwAccessTargetSizeUchar, WDF_DEVICE_HWACCESS_TARGET_TYPE enumeration, wdf.wdf_device_hwaccess_target_size, WdfDeviceHwAccessTargetSizeUlong, wudfddi_types/WdfDeviceHwAccessTargetSizeInvalid, wdfdevice/WdfDeviceHwAccessTargetSizeInvalid, WDF_DEVICE_HWACCESS_TARGET_TYPE, WdfDeviceHwAccessTargetSizeUchar, wudfddi_types/WDF_DEVICE_HWACCESS_TARGET_TYPE, wudfddi_types/WdfDeviceHwAccessTargetSizeUshort, WdfDeviceHwAccessTargetSizeUlong64, _WDF_DEVICE_HWACCESS_TARGET_SIZE, WDF_DEVICE_HWACCESS_TARGET_SIZE, wudfddi_types/PWDF_DEVICE_HWACCESS_TARGET_TYPE, wdfdevice/PWDF_DEVICE_HWACCESS_TARGET_TYPE, *PWDF_DEVICE_HWACCESS_TARGET_SIZE, wudfddi_types/WdfDeviceHwAccessTargetSizeUlong64, umdf.wdf_device_hwaccess_target_size, PWDF_DEVICE_HWACCESS_TARGET_TYPE, wdfdevice/WdfDeviceHwAccessTargetSizeUshort, wdfdevice/WdfDeviceHwAccessTargetSizeUlong, wdfdevice/WdfDeviceHwAccessTargetSizeMaximum, WdfDeviceHwAccessTargetSizeInvalid, WdfDeviceHwAccessTargetSizeMaximum, PWDF_DEVICE_HWACCESS_TARGET_TYPE enumeration pointer, wdfdevice/WdfDeviceHwAccessTargetSizeUchar, wudfddi_types/WdfDeviceHwAccessTargetSizeUlong, wdfdevice/WDF_DEVICE_HWACCESS_TARGET_TYPE, wudfddi_types/WdfDeviceHwAccessTargetSizeMaximum, WdfDeviceHwAccessTargetSizeUshort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
-	wudfddi_types.h
apiname:
-	WDF_DEVICE_HWACCESS_TARGET_TYPE
product: Windows
targetos: Windows
req.typenames: "*PWDF_DEVICE_HWACCESS_TARGET_SIZE, WDF_DEVICE_HWACCESS_TARGET_SIZE"
req.product: Windows 10 or later.
---

# _WDF_DEVICE_HWACCESS_TARGET_SIZE enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WDF_DEVICE_HWACCESS_TARGET_SIZE</b> enumeration is used internally by the framework. Do not use.


## -syntax


````
typedef enum __WDF_IO_TARGET_STATE { 
  WdfDeviceHwAccessTargetSizeInvalid  = 0,
  WdfDeviceHwAccessTargetSizeUchar    = 1,
  WdfDeviceHwAccessTargetSizeUshort   = 2,
  WdfDeviceHwAccessTargetSizeUlong    = 3,
  WdfDeviceHwAccessTargetSizeUlong64  = 4,
  WdfDeviceHwAccessTargetSizeMaximum  = 5
} WDF_DEVICE_HWACCESS_TARGET_TYPE, *PWDF_DEVICE_HWACCESS_TARGET_TYPE;
````


## -enum-fields




### -field WdfDeviceHwAccessTargetSizeInvalid


### -field WdfDeviceHwAccessTargetSizeUchar


### -field WdfDeviceHwAccessTargetSizeUshort


### -field WdfDeviceHwAccessTargetSizeUlong


### -field WdfDeviceHwAccessTargetSizeUlong64


### -field WdfDeviceHwAccessTargetSizeMaximum


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561319">UMDF Structures and Enumeration Types</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_HWACCESS_TARGET_SIZE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


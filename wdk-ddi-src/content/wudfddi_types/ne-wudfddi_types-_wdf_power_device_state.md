---
UID: NE:wudfddi_types._WDF_POWER_DEVICE_STATE
title: "_WDF_POWER_DEVICE_STATE"
author: windows-driver-content
description: The WDF_POWER_DEVICE_STATE enumeration contains values that identify the power state that a device might support.
old-location: wdf\wdf_power_device_state_umdf.htm
old-project: wdf
ms.assetid: de92bf06-b8fa-4c16-9216-95d68ca75111
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , *, *PWDF_POWER_DEVICE_STATE, ,, A, C, D, E, F, I, O, P, R, S, T, V, W, WDF_POWER_DEVICE_STATE, WDF_POWER_DEVICE_STATE enumeration, WdfPowerDeviceD0, WdfPowerDeviceD1, WdfPowerDeviceD2, WdfPowerDeviceD3, WdfPowerDeviceD3Final, WdfPowerDeviceInvalid, WdfPowerDeviceMaximum, WdfPowerDevicePrepareForHibernation, _, _WDF_POWER_DEVICE_STATE, umdf.wdf_power_device_state, umdfstructs_2037a598-edcf-4359-b17d-3d5f42eda92a.xml, wdf.wdf_power_device_state_umdf, wudfddi_types/WDF_POWER_DEVICE_STATE, wudfddi_types/WdfPowerDeviceD0, wudfddi_types/WdfPowerDeviceD1, wudfddi_types/WdfPowerDeviceD2, wudfddi_types/WdfPowerDeviceD3, wudfddi_types/WdfPowerDeviceD3Final, wudfddi_types/WdfPowerDeviceInvalid, wudfddi_types/WdfPowerDeviceMaximum, wudfddi_types/WdfPowerDevicePrepareForHibernation"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wudfddi_types.h
apiname:
-	WDF_POWER_DEVICE_STATE
product: Windows
targetos: Windows
req.typenames: WDF_POWER_DEVICE_STATE, *PWDF_POWER_DEVICE_STATE
req.product: Windows 10 or later.
---

# _WDF_POWER_DEVICE_STATE enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_power_device_state.md">WDF_POWER_DEVICE_STATE</a> enumeration contains values that identify the power state that a device might support.


## -syntax


````
typedef enum _WDF_POWER_DEVICE_STATE { 
  WdfPowerDeviceInvalid                = 0,
  WdfPowerDeviceD0                     = 1,
  WdfPowerDeviceD1                     = 2,
  WdfPowerDeviceD2                     = 3,
  WdfPowerDeviceD3                     = 4,
  WdfPowerDeviceD3Final                = 5,
  WdfPowerDevicePrepareForHibernation  = 6,
  WdfPowerDeviceMaximum                = ( WdfPowerDevicePrepareForHibernation + 1 )
} WDF_POWER_DEVICE_STATE;
````


## -enum-fields




### -field WdfPowerDeviceInvalid

The device power state is invalid or unknown.


### -field WdfPowerDeviceD0

The device supports the D0 device power state.


### -field WdfPowerDeviceD1

The device supports the D1 device power state.


### -field WdfPowerDeviceD2

The device supports the D2 device power state.


### -field WdfPowerDeviceD3

The device supports the D3 device power state.


### -field WdfPowerDeviceD3Final

The final time that the device enters the D3 device power state. Typically, this value means that the computer's power is being turned off or the device is being removed from the computer. The device might have been already removed.


### -field WdfPowerDevicePrepareForHibernation

The device supports hibernation files, and the computer is ready to hibernate by entering system state S4. The driver must not turn off the device.


### -field WdfPowerDeviceMaximum

Valid enumeration values were exceeded.


## -remarks



The framework supplies one of the values of <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_power_device_state.md">WDF_POWER_DEVICE_STATE</a> to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556799">IPnpCallback::OnD0Entry</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff556803">IPnpCallback::OnD0Exit</a> method to notify the UMDF driver about the power state of the device.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556799">IPnpCallback::OnD0Entry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556803">IPnpCallback::OnD0Exit</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_POWER_DEVICE_STATE enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


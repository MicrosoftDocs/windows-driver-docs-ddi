---
UID: NF:wdfdevice.WdfDeviceGetHardwareRegisterMappedAddress
title: WdfDeviceGetHardwareRegisterMappedAddress function
author: windows-driver-content
description: A driver calls WdfDeviceGetHardwareRegisterMappedAddress to get the user-mode mapped address of the memory resource it mapped previously using WdfDeviceMapIoSpace.
old-location: wdf\wdfdevicegethardwareregistermappedaddress.htm
tech.root: wdf
ms.assetid: 4D172D39-0D28-4950-B428-330D5B4D0654
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDeviceGetHardwareRegisterMappedAddress, WdfDeviceGetHardwareRegisterMappedAddress function, wdf.wdfdevicegethardwareregistermappedaddress, wdfdevice/WdfDeviceGetHardwareRegisterMappedAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	WUDFx02000.dll
api_name:
-	WdfDeviceGetHardwareRegisterMappedAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceGetHardwareRegisterMappedAddress function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

A driver calls <b>WdfDeviceGetHardwareRegisterMappedAddress</b> to get the user-mode mapped address of the memory resource it mapped previously using <a href="https://msdn.microsoft.com/library/windows/hardware/dn265605">WdfDeviceMapIoSpace</a>.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PseudoBaseAddress [in]

The address of a location that receives a pointer to the pseudo base address.


## -returns



User-mode base address of the resources mapped earlier using <a href="https://msdn.microsoft.com/library/windows/hardware/dn265605">WdfDeviceMapIoSpace</a>.




## -remarks



This function is the UMDF version 2 equivalent of <a href="https://msdn.microsoft.com/94852404-301F-4C09-81D2-CEDEECFCD6BD">IWDFDevice3::GetHardwareRegisterMappedAddress</a>.

After the driver calls <b>WdfDeviceGetHardwareRegisterMappedAddress</b>, it can access the user-mode address directly to read and write to the register.


<div class="alert"><b>Note</b>  This is not the recommended approach for accessing registers because it prevents UMDF from doing any validation on the access.</div>
<div> </div>


If you do use <b>WdfDeviceGetHardwareRegisterMappedAddress</b>, you must set the <b>UmdfRegisterAccessMode</b> INF directive to <b>RegisterAccessUsingUserModeMapping</b>.  For more information about UMDF  INF directives, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/specifying-wdf-directives-in-inf-files">Specifying WDF Directives in INF Files</a>.




## -see-also




<a href="https://msdn.microsoft.com/94852404-301F-4C09-81D2-CEDEECFCD6BD">IWDFDevice3::GetHardwareRegisterMappedAddress</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265605">WdfDeviceMapIoSpace</a>
 

 


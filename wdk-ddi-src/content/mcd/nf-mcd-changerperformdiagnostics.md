---
UID: NF:mcd.ChangerPerformDiagnostics
title: ChangerPerformDiagnostics function
author: windows-driver-content
description: ChangerPerformDiagnostics performs diagnostic tests on the changer device.
old-location: storage\changerperformdiagnostics.htm
tech.root: storage
ms.assetid: 87767b2b-8ca3-4d19-8719-673562246a41
ms.date: 03/29/2018
ms.keywords: ChangerPerformDiagnostics, ChangerPerformDiagnostics function [Storage Devices], chgrmini_dd38573a-a1cc-4b7b-abdf-0a200ba11d88.xml, mcd/ChangerPerformDiagnostics, storage.changerperformdiagnostics
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
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
-	HeaderDef
api_location:
-	mcd.h
api_name:
-	ChangerPerformDiagnostics
product:
- Windows
targetos: Windows
req.typenames: 
---

# ChangerPerformDiagnostics function


## -description


<b>ChangerPerformDiagnostics</b> performs diagnostic tests on the changer device.


## -parameters




### -param DeviceObject [in]

Pointer to the device object that represents the changer.


### -param changerDeviceError

<p>Pointer to the buffer of type <a href="https://msdn.microsoft.com/library/Ff568029(v=VS.85).aspx"><b>WMI_CHANGER_PROBLEM_DEVICE_ERROR</b></a> in which the minidriver returns the diagnostic information.</p>




## -returns



<b>ChangerPerformDiagnostics</b> returns the status returned by the system port driver or one of the following values:
      

STATUS_SUCCESS

STATUS_INSUFFICIENT_RESOURCES

STATUS_BUFFER_TOO_SMALL




## -remarks



<b>ChangerPerformDiagnostics</b> routine performs diagnostic tests on the changer device, and reports the problem to the caller. The kind of tests performed depends on the diagnostics support provided by the device. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551453">CHANGER_DEVICE_PROBLEM_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568029">WMI_CHANGER_PROBLEM_DEVICE_ERROR</a>
 

 


---
UID: NF:wdm.IoGetFunctionCodeFromCtlCode
title: IoGetFunctionCodeFromCtlCode macro
author: windows-driver-content
description: The IoGetFunctionCodeFromCtlCode macro returns the value of the function code contained in an I/O control code.
old-location: kernel\iogetfunctioncodefromctlcode.htm
old-project: kernel
ms.assetid: 8bbde78d-49f4-4181-9d92-312010322a7a
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoGetFunctionCodeFromCtlCode, IoGetFunctionCodeFromCtlCode function [Kernel-Mode Driver Architecture], k104_211d730a-0df4-45f4-af58-25d2609c7696.xml, kernel.iogetfunctioncodefromctlcode, wdm/IoGetFunctionCodeFromCtlCode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	IoGetFunctionCodeFromCtlCode
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetFunctionCodeFromCtlCode macro


## -description


The <b>IoGetFunctionCodeFromCtlCode</b> macro returns the value of the function code contained in an I/O control code.


## -parameters




### -param ControlCode [in]

The IOCTL_<i>XXX</i> (or FSCTL_<i>XXX</i>) value, which can be obtained from the driver's I/O stack location of the IRP at <b>Parameters.DeviceIoControl.IoControlCode</b>.


## -remarks



For information about the layout of IOCTL codes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565406">Using I/O Control Codes</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a>
 

 


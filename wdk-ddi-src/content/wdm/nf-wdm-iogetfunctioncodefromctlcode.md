---
UID: NF:wdm.IoGetFunctionCodeFromCtlCode
title: IoGetFunctionCodeFromCtlCode macro (wdm.h)
description: The IoGetFunctionCodeFromCtlCode macro returns the value of the function code contained in an I/O control code.
old-location: kernel\iogetfunctioncodefromctlcode.htm
tech.root: kernel
ms.assetid: 8bbde78d-49f4-4181-9d92-312010322a7a
ms.date: 04/30/2018
ms.keywords: IoGetFunctionCodeFromCtlCode, IoGetFunctionCodeFromCtlCode function [Kernel-Mode Driver Architecture], k104_211d730a-0df4-45f4-af58-25d2609c7696.xml, kernel.iogetfunctioncodefromctlcode, wdm/IoGetFunctionCodeFromCtlCode
ms.topic: macro
f1_keywords:
 - "wdm/IoGetFunctionCodeFromCtlCode"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- IoGetFunctionCodeFromCtlCode
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetFunctionCodeFromCtlCode macro


## -description


The <b>IoGetFunctionCodeFromCtlCode</b> macro returns the value of the function code contained in an I/O control code.


## -parameters




### -param ControlCode [in]

The IOCTL_<i>XXX</i> (or FSCTL_<i>XXX</i>) value, which can be obtained from the driver's I/O stack location of the IRP at <b>Parameters.DeviceIoControl.IoControlCode</b>.


## -returns
**IoGetFunctionCodeFromCtlCode** returns the value of the Function part of the given IOCTL_XXX code.

## -remarks



For information about the layout of IOCTL codes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-i-o-control-codes">Using I/O Control Codes</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuilddeviceiocontrolrequest">IoBuildDeviceIoControlRequest</a>
 

 


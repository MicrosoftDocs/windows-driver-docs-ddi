---
UID: NF:wdm.IoGetFunctionCodeFromCtlCode
title: IoGetFunctionCodeFromCtlCode macro
author: windows-driver-content
description: The IoGetFunctionCodeFromCtlCode macro returns the value of the function code contained in an I/O control code.
old-location: kernel\iogetfunctioncodefromctlcode.htm
old-project: kernel
ms.assetid: 8bbde78d-49f4-4181-9d92-312010322a7a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , C, F, G, I, IoGetFunctionCodeFromCtlCode, IoGetFunctionCodeFromCtlCode function [Kernel-Mode Driver Architecture], c, d, e, i, k104_211d730a-0df4-45f4-af58-25d2609c7696.xml, kernel.iogetfunctioncodefromctlcode, l, m, n, o, r, t, u, wdm/IoGetFunctionCodeFromCtlCode"
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
req.lib: wdm.h
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	IoGetFunctionCodeFromCtlCode
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetFunctionCodeFromCtlCode macro


## -description


The <b>IoGetFunctionCodeFromCtlCode</b> macro returns the value of the function code contained in an I/O control code.


## -syntax


````
ULONG IoGetFunctionCodeFromCtlCode(
  _In_ ULONG ControlCode
);
````


## -parameters




### -param ControlCode [in]

The IOCTL_<i>XXX</i> (or FSCTL_<i>XXX</i>) value, which can be obtained from the driver's I/O stack location of the IRP at <b>Parameters.DeviceIoControl.IoControlCode</b>.


## -remarks



For information about the layout of IOCTL codes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565406">Using I/O Control Codes</a>.




## -see-also

<a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetFunctionCodeFromCtlCode function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


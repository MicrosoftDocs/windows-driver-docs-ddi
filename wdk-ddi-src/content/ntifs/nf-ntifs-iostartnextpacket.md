---
UID: NF:ntifs.IoStartNextPacket
title: IoStartNextPacket function
author: windows-driver-content
description: The IoStartNextPacket routine dequeues the next IRP, if any, from the given device object's associated device queue and calls the driver's StartIo routine.
old-location: kernel\iostartnextpacket.htm
old-project: kernel
ms.assetid: f1197dfd-03d7-4ac2-8f11-60da413e32b2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.iostartnextpacket, wdm/IoStartNextPacket, IoStartNextPacket routine [Kernel-Mode Driver Architecture], IoStartNextPacket, k104_5a02a1fa-cf0e-43b0-a4e8-db1da8ad110c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch, SpinLockSafe, StartIoRecursion, HwStorPortProhibitedDDIs, IrqlDispatch(storport), SpinLockSafe(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoStartNextPacket
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoStartNextPacket function


## -description


The <b>IoStartNextPacket</b> routine dequeues the next IRP, if any, from the given device object's associated device queue and calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine.


## -syntax


````
VOID IoStartNextPacket(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ BOOLEAN        Cancelable
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object for which the IRP is to be dequeued.


### -param Cancelable [in]

Specifies whether IRPs in the device queue can be canceled. 


## -returns


None



## -remarks


If there are no IRPs currently in the device queue for the target <i>DeviceObject</i>, this routine simply returns control to the caller.

If the driver passed a pointer to a cancel routine when it called <b>IoStartPacket</b>, it should pass <b>TRUE</b> in the <i>Cancelable</i> parameter. If <i>Cancelable </i>is <b>TRUE</b>, the I/O manager will use the cancel spin lock to protect the device queue and the current IRP. 

Drivers that do not have a <i>StartIo</i> routine cannot call <b>IoStartNextPacket</b>.

Drivers that call <b>IoStartNextPacket </b>from their <i>StartIo</i> routine should be aware of recursion issues. If a driver can call <b>IoStartNextPacket</b> on a large number of requests in succession from its <i>StartIo</i> routine (for example, when a device error occurs and the driver is clearing out it device queue), you should set the <i>DeferredStartIo</i> attribute for the device by using <a href="..\ntifs\nf-ntifs-iosetstartioattributes.md">IoSetStartIoAttributes</a> routine. This attribute ensures that the next packet will not be issued until the previous <i>StartIo</i> call returns.

Callers of <b>IoStartNextPacket</b> must be running at IRQL = DISPATCH_LEVEL. Usually, this routine is called from a device driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff544079">DpcForIsr</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a> routine, both of which are run at IRQL = DISPATCH_LEVEL.



## -see-also

<a href="..\ntifs\nf-ntifs-iostartnextpacketbykey.md">IoStartNextPacketByKey</a>

<a href="..\ntifs\nf-ntifs-iostartpacket.md">IoStartPacket</a>

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

<a href="..\ntifs\nf-ntifs-iosetstartioattributes.md">IoSetStartIoAttributes</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoStartNextPacket routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


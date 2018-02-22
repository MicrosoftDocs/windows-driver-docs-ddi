---
UID: NF:ntifs.IoStartNextPacketByKey
title: IoStartNextPacketByKey function
author: windows-driver-content
description: The IoStartNextPacketByKey routine dequeues the next I/O request packet from the specified device object's associated device queue according to a specified sort-key value and calls the driver's StartIo routine with that IRP.
old-location: kernel\iostartnextpacketbykey.htm
old-project: kernel
ms.assetid: 25cf9026-fd5d-4998-b7ff-f7be048ef2a1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoStartNextPacketByKey routine [Kernel-Mode Driver Architecture], k104_f2248acf-8071-43a6-b5f9-bc3bc178469b.xml, kernel.iostartnextpacketbykey, wdm/IoStartNextPacketByKey, IoStartNextPacketByKey
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
-	IoStartNextPacketByKey
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoStartNextPacketByKey function


## -description


The <b>IoStartNextPacketByKey</b> routine dequeues the next I/O request packet from the specified device object's associated device queue according to a specified sort-key value and calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine with that IRP.


## -syntax


````
VOID IoStartNextPacketByKey(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ BOOLEAN        Cancelable,
  _In_ ULONG          Key
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object for which the IRP is to be dequeued.


### -param Cancelable [in]

Specifies whether IRPs in the device queue can be canceled.


### -param Key [in]

Specifies the sort key that determines which entry to remove from the queue.


## -returns



None




## -remarks



If there are no IRPs currently in the device queue for the target device object, this routine simply returns control to the caller.

If the driver passed a pointer to a cancel routine when it called <b>IoStartPacket</b>, it should pass <b>TRUE</b> in the <i>Cancelable</i> parameter. If <i>Cancelable</i>  is <b>TRUE</b>, the I/O manager will use the cancel spin lock to protect the device queue and the current IRP. 

Drivers that do not have a <i>StartIo</i> routine cannot call <b>IoStartNextPacketByKey</b>.

Callers of <b>IoStartNextPacketByKey</b> must be running at IRQL &lt;= DISPATCH_LEVEL. Usually, this routine is called from a device driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff544079">DpcForIsr</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a> routine, both of which are run at IRQL = DISPATCH_LEVEL.




## -see-also

<a href="..\ntifs\nf-ntifs-iostartpacket.md">IoStartPacket</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="..\ntifs\nf-ntifs-iostartnextpacket.md">IoStartNextPacket</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoStartNextPacketByKey routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


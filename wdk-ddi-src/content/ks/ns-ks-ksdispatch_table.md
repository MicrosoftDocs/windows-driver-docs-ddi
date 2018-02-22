---
UID: NS:ks.KSDISPATCH_TABLE
title: KSDISPATCH_TABLE
author: windows-driver-content
description: The KSDISPATCH_TABLE structure contains pointers to minidriver implemented IRP dispatch routines.
old-location: stream\ksdispatch_table.htm
old-project: stream
ms.assetid: baa45ce7-3dcd-4383-99f2-aeb664a03190
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: PKSDISPATCH_TABLE structure pointer [Streaming Media Devices], ks/KSDISPATCH_TABLE, ks/PKSDISPATCH_TABLE, KSDISPATCH_TABLE, stream.ksdispatch_table, PKSDISPATCH_TABLE, KSDISPATCH_TABLE structure [Streaming Media Devices], ks-struct_c1daf962-90e2-495e-9531-c23716ee9d68.xml, *PKSDISPATCH_TABLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSDISPATCH_TABLE
product: Windows
targetos: Windows
req.typenames: KSDISPATCH_TABLE, *PKSDISPATCH_TABLE
---

# KSDISPATCH_TABLE structure


## -description


The KSDISPATCH_TABLE structure contains pointers to minidriver implemented IRP dispatch routines.


## -syntax


````
typedef struct {
  PDRIVER_DISPATCH        DeviceIoControl;
  PDRIVER_DISPATCH        Read;
  PDRIVER_DISPATCH        Write;
  PDRIVER_DISPATCH        Flush;
  PDRIVER_DISPATCH        Close;
  PDRIVER_DISPATCH        QuerySecurity;
  PDRIVER_DISPATCH        SetSecurity;
  PFAST_IO_DEVICE_CONTROL FastDeviceIoControl;
  PFAST_IO_READ           FastRead;
  PFAST_IO_WRITE          FastWrite;
} KSDISPATCH_TABLE, *PKSDISPATCH_TABLE;
````


## -struct-fields




### -field DeviceIoControl

Specifies the minidriver's routine to dispatch <a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a> IRPs to.


### -field Read

Specifies the minidriver's routine to dispatch <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> IRPs to.


### -field Write

Specifies the minidriver's routine to dispatch <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a> IRPs to.


### -field Flush

Specifies the minidriver's routine to dispatch <a href="https://msdn.microsoft.com/library/windows/hardware/ff549235">IRP_MJ_FLUSH_BUFFERS</a> IRPs to.


### -field Close

Specifies the minidriver's routine to dispatch <a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a> IRPs to.


### -field QuerySecurity

Specifies the minidriver's routine to dispatch <a href="https://msdn.microsoft.com/library/windows/hardware/ff549298">IRP_MJ_QUERY_SECURITY</a> IRPs to.


### -field SetSecurity

Specifies the minidriver's routine to dispatch <a href="https://msdn.microsoft.com/library/windows/hardware/ff549407">IRP_MJ_SET_SECURITY</a> IRPs to.


### -field FastDeviceIoControl

Specifies the minidriver's routine to dispatch fast device I/O control requests to.


### -field FastRead

Specifies the minidriver's routine to dispatch fast read requests to.


### -field FastWrite

Specifies the minidriver's routine to dispatch fast write requests to.


## -remarks



A pointer to a dispatch table is contained in the opaque object header that is the first element of data pointed to by the file object's <b>FsContext</b> field.

For more information about minidriver implemented IRP dispatch routines, see <a href="..\ks\nf-ks-kssetmajorfunctionhandler.md">KsSetMajorFunctionHandler</a>, and <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>.




## -see-also

<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>



<a href="..\ks\nf-ks-kssetmajorfunctionhandler.md">KsSetMajorFunctionHandler</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSDISPATCH_TABLE structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


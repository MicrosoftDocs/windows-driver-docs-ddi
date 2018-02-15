---
UID: NS:iscsiop._SendTargets_OUT
title: "_SendTargets_OUT"
author: windows-driver-content
description: The SendTargets_OUT structure holds the output data for the SendTargets method.
old-location: storage\sendtargets_out.htm
old-project: storage
ms.assetid: 82efeeb9-1167-4114-9d88-7ef66f613f80
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSendTargets_OUT, SendTargets_OUT structure [Storage Devices], *PSendTargets_OUT, iscsiop/SendTargets_OUT, PSendTargets_OUT structure pointer [Storage Devices], structs-iSCSI_c54a2d75-d780-4605-bdaf-5953f7ce5008.xml, storage.sendtargets_out, _SendTargets_OUT, iscsiop/PSendTargets_OUT, SendTargets_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
-	iscsiop.h
apiname:
-	SendTargets_OUT
product: Windows
targetos: Windows
req.typenames: SendTargets_OUT, *PSendTargets_OUT
---

# _SendTargets_OUT structure


## -description


The SendTargets_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565526">SendTargets</a> method.


## -syntax


````
typedef struct _SendTargets_OUT {
  ULONG Status;
  ULONG ResponseSize;
  UCHAR Response[1];
} SendTargets_OUT, *PSendTargets_OUT;
````


## -struct-fields




### -field Status

The status of the <b>SendTargets</b> method. This member will contain 0 if the SEND TARGETS operation succeeds and ISDSC_SCSI_REQUEST_FAILED if the operation fails. If the SEND TARGETS operation fails, <b>ScsiStatus</b> will contain the SCSI status of the SCSI command. SCSI status qualifiers are documented in the <i>SCSI Primary Commands</i> specification. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.  


### -field ResponseSize

The size, in bytes, of the buffer at Response.


### -field Response

A buffer that holds the response data that the target returns. Response to SendTargets in UTF8 characters. NOTE: This field is a variable length array.


## -remarks



You must implement this method.




## -see-also

<a href="..\iscsiop\ns-iscsiop-_sendtargets_in.md">SendTargets_IN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565526">SendTargets</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SendTargets_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


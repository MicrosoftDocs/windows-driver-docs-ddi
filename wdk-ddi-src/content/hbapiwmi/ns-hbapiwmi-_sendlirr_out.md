---
UID: NS:hbapiwmi._SendLIRR_OUT
title: "_SendLIRR_OUT"
author: windows-driver-content
description: The SendLIRR_OUT structure is used to report the output parameter data of the SendLIRR WMI method to the WMI client.
old-location: storage\sendlirr_out.htm
old-project: storage
ms.assetid: 842842c2-ed79-4c8a-b9c1-d73c47998f91
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSendLIRR_OUT, SendLIRR_OUT, SendLIRR_OUT structure [Storage Devices], *PSendLIRR_OUT, hbapiwmi/PSendLIRR_OUT, structs-Fibre_193ae454-313d-4ada-a161-39c403226edf.xml, hbapiwmi/SendLIRR_OUT, storage.sendlirr_out, PSendLIRR_OUT structure pointer [Storage Devices], _SendLIRR_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
-	hbapiwmi.h
apiname:
-	SendLIRR_OUT
product: Windows
targetos: Windows
req.typenames: "*PSendLIRR_OUT, SendLIRR_OUT"
---

# _SendLIRR_OUT structure


## -description


The SendLIRR_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565419">SendLIRR</a> WMI method to the WMI client.


## -syntax


````
typedef struct _SendLIRR_OUT {
  ULONG HBAStatus;
  ULONG TotalRspBufferSize;
  ULONG ActualRspBufferSize;
  UCHAR RspBuffer[1];
} SendLIRR_OUT, *PSendLIRR_OUT;
````


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>. 


### -field TotalRspBufferSize

Contains the size in bytes of the results of the LIRR command. 


### -field ActualRspBufferSize

Contains the size in bytes of the data that was actually retrieved. 


### -field RspBuffer

Contains the results of the LIRR command. 


## -remarks



The WMI tool suite generates a declaration of the SendLIRR_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565419">SendLIRR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SendLIRR_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


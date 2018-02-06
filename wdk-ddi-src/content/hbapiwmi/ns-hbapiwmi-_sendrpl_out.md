---
UID: NS:hbapiwmi._SendRPL_OUT
title: "_SendRPL_OUT"
author: windows-driver-content
description: The SendRPL_OUT structure is used to report the output parameter data of the SendRPL WMI method to the WMI client.
old-location: storage\sendrpl_out.htm
old-project: storage
ms.assetid: 36ca3d6e-7012-4bbb-a2a0-e19708aa1058
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSendRPL_OUT, *PSendRPL_OUT, SendRPL_OUT, _SendRPL_OUT, PSendRPL_OUT structure pointer [Storage Devices], SendRPL_OUT structure [Storage Devices], hbapiwmi/SendRPL_OUT, storage.sendrpl_out, structs-Fibre_aef41c84-1718-4e82-aeae-d0280d6cf3b1.xml, hbapiwmi/PSendRPL_OUT
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
-	SendRPL_OUT
product: Windows
targetos: Windows
req.typenames: SendRPL_OUT, *PSendRPL_OUT
---

# _SendRPL_OUT structure


## -description


The SendRPL_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565488">SendRPL</a> WMI method to the WMI client.


## -syntax


````
typedef struct _SendRPL_OUT {
  ULONG HBAStatus;
  ULONG TotalRspBufferSize;
  ULONG ActualRspBufferSize;
  UCHAR RspBuffer[1];
} SendRPL_OUT, *PSendRPL_OUT;
````


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>. 


### -field TotalRspBufferSize

Contains the size in bytes of the results of the read port list (RPL) command. 


### -field ActualRspBufferSize

Contains the size in bytes of the data that was actually retrieved. 


### -field RspBuffer

Contains the results of the read port list (RPL) command. 


## -remarks


The WMI tool suite generates a declaration of the SendRPL_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565488">SendRPL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SendRPL_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


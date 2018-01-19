---
UID: NS:hbapiwmi._SendRNIDV2_IN
title: _SendRNIDV2_IN
author: windows-driver-content
description: The SendRNIDV2_IN structure is used to deliver input parameter data to the SendRNIDV2 WMI method.
old-location: storage\sendrnidv2_in.htm
old-project: storage
ms.assetid: b9c0833d-96ac-41cb-815f-b2df27f46cb4
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SendRNIDV2_IN, *PSendRNIDV2_IN, SendRNIDV2_IN
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
req.alt-api: SendRNIDV2_IN
req.alt-loc: hbapiwmi.h
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
req.typenames: *PSendRNIDV2_IN, SendRNIDV2_IN
---

# _SendRNIDV2_IN structure



## -description
The SendRNIDV2_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565463">SendRNIDV2</a> WMI method.



## -syntax

````
typedef struct _SendRNIDV2_IN {
  UCHAR PortWWN[8];
  UCHAR DestWWN[8];
  ULONG DestFCID;
  ULONG NodeIdDataFormat;
} SendRNIDV2_IN, *PSendRNIDV2_IN;
````


## -struct-fields

### -field PortWWN

Contains a worldwide name for the local port through which the version 2 request node identification data (RNIDV2) command is sent. 


### -field DestWWN

Contains a worldwide name for the destination port. 


### -field DestFCID

Contains an address identifier of the destination port. For a description of the values that this member can have, see the T11 committee's specification for <i>Fibre Channel HBA API</i>.


### -field NodeIdDataFormat

Indicates the node identification data format. For a description of the values that this member can have, see the T11 committee's specification for <i>Fibre Channel HBA API</i>. 


## -remarks
The WMI tool suite generates a declaration of the SendRNIDV2_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565463">SendRNIDV2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SendRNIDV2_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


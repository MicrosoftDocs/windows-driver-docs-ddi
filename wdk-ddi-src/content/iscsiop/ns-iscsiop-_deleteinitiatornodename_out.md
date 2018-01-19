---
UID: NS:iscsiop._DeleteInitiatorNodeName_OUT
title: _DeleteInitiatorNodeName_OUT
author: windows-driver-content
description: The DeleteInitiatorNodeName_OUT structure holds the output data for the DeleteInitiatorNodeName method.
old-location: storage\deleteinitiatornodename_out.htm
old-project: storage
ms.assetid: 105f6687-ea0f-45e9-be44-eafdd06156eb
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DeleteInitiatorNodeName_OUT, DeleteInitiatorNodeName_OUT, *PDeleteInitiatorNodeName_OUT
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
req.alt-api: DeleteInitiatorNodeName_OUT
req.alt-loc: iscsiop.h
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
req.typenames: DeleteInitiatorNodeName_OUT, *PDeleteInitiatorNodeName_OUT
---

# _DeleteInitiatorNodeName_OUT structure



## -description
The DeleteInitiatorNodeName_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552500">DeleteInitiatorNodeName</a> method.



## -syntax

````
typedef struct _DeleteInitiatorNodeName_OUT {
  ULONG Status;
} DeleteInitiatorNodeName_OUT, *PDeleteInitiatorNodeName_OUT;
````


## -struct-fields

### -field Status

The status of the <b>DeleteInitiatorNodeName</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>. 


## -remarks
It is optional that you implement this method.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552500">DeleteInitiatorNodeName</a>
</dt>
<dt>
<a href="..\iscsiop\ns-iscsiop-_deleteinitiatornodename_in.md">DeleteInitiatorNodeName_IN</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DeleteInitiatorNodeName_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


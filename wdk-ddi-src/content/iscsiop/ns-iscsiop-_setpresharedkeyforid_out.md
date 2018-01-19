---
UID: NS:iscsiop._SetPresharedKeyForId_OUT
title: _SetPresharedKeyForId_OUT
author: windows-driver-content
description: The SetPresharedKeyForId_OUT structure holds the output data for the SetPresharedKeyForId method.
old-location: storage\setpresharedkeyforid_out.htm
old-project: storage
ms.assetid: 839041be-bb8c-4e02-a260-e9adcec98ff3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SetPresharedKeyForId_OUT, SetPresharedKeyForId_OUT, *PSetPresharedKeyForId_OUT
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
req.alt-api: SetPresharedKeyForId_OUT
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
req.typenames: SetPresharedKeyForId_OUT, *PSetPresharedKeyForId_OUT
---

# _SetPresharedKeyForId_OUT structure



## -description
The SetPresharedKeyForId_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565800">SetPresharedKeyForId</a> method.



## -syntax

````
typedef struct _SetPresharedKeyForId_OUT {
  ULONG Status;
} SetPresharedKeyForId_OUT, *PSetPresharedKeyForId_OUT;
````


## -struct-fields

### -field Status

On output, the status of the <b>SetPresharedKeyForId</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>. 


## -remarks
You must implement this method.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565800">SetPresharedKeyForId</a>
</dt>
<dt>
<a href="..\iscsiop\ns-iscsiop-_setpresharedkeyforid_in.md">SetPresharedKeyForId_IN</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetPresharedKeyForId_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


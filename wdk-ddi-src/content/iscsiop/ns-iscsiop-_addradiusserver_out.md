---
UID: NS:iscsiop._AddRADIUSServer_OUT
title: _AddRADIUSServer_OUT
author: windows-driver-content
description: The AddRADIUSServer_OUT structure holds the output data for the AddRADIUSServer method.
old-location: storage\addradiusserver_out.htm
old-project: storage
ms.assetid: 512e66f6-d91f-4351-ba55-02ae3e84102e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _AddRADIUSServer_OUT, *PAddRADIUSServer_OUT, AddRADIUSServer_OUT
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
req.alt-api: AddRADIUSServer_OUT
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
req.typenames: *PAddRADIUSServer_OUT, AddRADIUSServer_OUT
---

# _AddRADIUSServer_OUT structure



## -description
The AddRADIUSServer_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550133">AddRADIUSServer</a> method.



## -syntax

````
typedef struct _AddRADIUSServer_OUT {
  ULONG Status;
} AddRADIUSServer_OUT, *PAddRADIUSServer_OUT;
````


## -struct-fields

### -field Status

On output from <b>AddRADIUSServer</b>, the status of the <b>AddRADIUSServer</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.


## -remarks
It is optional that you implement this method.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550133">AddRADIUSServer</a>
</dt>
<dt>
<a href="..\iscsiop\ns-iscsiop-_addradiusserver_in.md">AddRADIUSServer_IN</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563091">MSiSCSI_Operations WMI Class</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AddRADIUSServer_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


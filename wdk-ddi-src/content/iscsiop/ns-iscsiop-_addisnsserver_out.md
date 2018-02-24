---
UID: NS:iscsiop._AddiSNSServer_OUT
title: "_AddiSNSServer_OUT"
author: windows-driver-content
description: The AddiSNSServer_OUT structure holds the output data for the user-mode AddISNSServer method.
old-location: storage\addisnsserver_out.htm
old-project: storage
ms.assetid: f1c02d19-9e96-4fd6-b950-ae02b6f3bba4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: structs-iSCSI_d1d3f4d6-6c48-4f6d-bc5e-9449a4b87d2b.xml, PAddiSNSServer_OUT structure pointer [Storage Devices], iscsiop/AddiSNSServer_OUT, storage.addisnsserver_out, AddiSNSServer_OUT, AddiSNSServer_OUT structure [Storage Devices], PAddiSNSServer_OUT, iscsiop/PAddiSNSServer_OUT, _AddiSNSServer_OUT, *PAddiSNSServer_OUT
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
-	AddiSNSServer_OUT
product: Windows
targetos: Windows
req.typenames: AddiSNSServer_OUT, *PAddiSNSServer_OUT
---

# _AddiSNSServer_OUT structure


## -description


The AddiSNSServer_OUT structure holds the output data for the user-mode <b>AddISNSServer</b> method.


## -syntax


````
typedef struct _AddiSNSServer_OUT {
  ULONG Status;
} AddiSNSServer_OUT, *PAddiSNSServer_OUT;
````


## -struct-fields




### -field Status

On output from <b>AddISNSServer</b>, the status of the <b>AddISNSServer</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.  


## -remarks



It is optional that you implement this method.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563091">MSiSCSI_Operations WMI Class</a>



<a href="..\iscsiop\ns-iscsiop-_addisnsserver_in.md">AddiSNSServer_IN</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AddiSNSServer_OUT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


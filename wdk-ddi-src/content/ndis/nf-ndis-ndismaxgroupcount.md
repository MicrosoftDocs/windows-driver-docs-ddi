---
UID: NF:ndis.NdisMaxGroupCount
title: NdisMaxGroupCount function
author: windows-driver-content
description: The NdisMaxGroupCount function returns the maximum number of processor groups in the local computer system.
old-location: netvista\ndismaxgroupcount.htm
old-project: netvista
ms.assetid: 080707c5-cf46-4066-a241-684cdae37fee
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ndis/NdisMaxGroupCount, netvista.ndismaxgroupcount, NdisMaxGroupCount, NdisMaxGroupCount function [Network Drivers Starting with Windows Vista], ndis_processor_group_ref_5744be61-71b7-4abc-ad66-30b26558c0ac.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisMaxGroupCount
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisMaxGroupCount function


## -description


The
  <b>NdisMaxGroupCount</b> function returns the maximum number of processor groups in the local computer
  system.


## -syntax


````
USHORT NdisMaxGroupCount(void);
````


## -parameters






## -returns



<b>NdisMaxGroupCount</b> returns a USHORT value for the maximum number of processor groups that are
     included in the local computer system. The number of groups is a zero-based value.




## -remarks



NDIS drivers call the 
    <b>NdisMaxGroupCount</b> function to obtain the maximum number of processor groups that are included in
    the local computer system.

To obtain the number of groups that are currently active, call the 
    <a href="..\ndis\nf-ndis-ndisactivegroupcount.md">NdisActiveGroupCount</a> function.




## -see-also

<a href="..\ndis\nf-ndis-ndisactivegroupcount.md">NdisActiveGroupCount</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMaxGroupCount function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


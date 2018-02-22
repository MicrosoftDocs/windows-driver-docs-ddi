---
UID: NS:iscsiop._DeleteInitiatorNodeName_IN
title: "_DeleteInitiatorNodeName_IN"
author: windows-driver-content
description: The DeleteInitiatorNodeName_IN structure holds the input data for the DeleteInitiatorNodeName method, which is used to delete an initiator node name.
old-location: storage\deleteinitiatornodename_in.htm
old-project: storage
ms.assetid: 10b6660c-7f48-4717-89d4-d6a5eb6594c8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDeleteInitiatorNodeName_IN, iscsiop/PDeleteInitiatorNodeName_IN, structs-iSCSI_2b687a5a-17af-4eda-b48f-8e7ca06024f2.xml, iscsiop/DeleteInitiatorNodeName_IN, DeleteInitiatorNodeName_IN structure [Storage Devices], DeleteInitiatorNodeName_IN, PDeleteInitiatorNodeName_IN, _DeleteInitiatorNodeName_IN, PDeleteInitiatorNodeName_IN structure pointer [Storage Devices], storage.deleteinitiatornodename_in"
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
-	DeleteInitiatorNodeName_IN
product: Windows
targetos: Windows
req.typenames: DeleteInitiatorNodeName_IN, *PDeleteInitiatorNodeName_IN
---

# _DeleteInitiatorNodeName_IN structure


## -description


The DeleteInitiatorNodeName_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552500">DeleteInitiatorNodeName</a> method, which is used to delete an initiator node name.


## -syntax


````
typedef struct _DeleteInitiatorNodeName_IN {
  WCHAR DeletedInitiatorName[223 + 1];
} DeleteInitiatorNodeName_IN, *PDeleteInitiatorNodeName_IN;
````


## -struct-fields




### -field DeletedInitiatorName

The iSCSI initiator node name that is to be deleted.


## -remarks



It is optional that you implement this method.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552500">DeleteInitiatorNodeName</a>



<a href="..\iscsiop\ns-iscsiop-_deleteinitiatornodename_out.md">DeleteInitiatorNodeName_OUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DeleteInitiatorNodeName_IN structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


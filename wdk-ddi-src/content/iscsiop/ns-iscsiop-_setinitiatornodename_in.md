---
UID: NS:iscsiop._SetInitiatorNodeName_IN
title: "_SetInitiatorNodeName_IN"
author: windows-driver-content
description: The SetInitiatorNodeName_IN structure holds the input data for the SetInitiatorNodeName method.
old-location: storage\setinitiatornodename_in.htm
old-project: storage
ms.assetid: 58af1872-23bf-44f2-9ef4-271f0ddef5d5
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: SetInitiatorNodeName_IN structure [Storage Devices], _SetInitiatorNodeName_IN, *PSetInitiatorNodeName_IN, PSetInitiatorNodeName_IN, iscsiop/SetInitiatorNodeName_IN, SetInitiatorNodeName_IN, iscsiop/PSetInitiatorNodeName_IN, PSetInitiatorNodeName_IN structure pointer [Storage Devices], structs-iSCSI_fac4e524-8266-4135-9211-564d1ea2a952.xml, storage.setinitiatornodename_in
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
-	SetInitiatorNodeName_IN
product: Windows
targetos: Windows
req.typenames: SetInitiatorNodeName_IN, *PSetInitiatorNodeName_IN
---

# _SetInitiatorNodeName_IN structure


## -description


The SetInitiatorNodeName_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565706">SetInitiatorNodeName</a> method.


## -syntax


````
typedef struct _SetInitiatorNodeName_IN {
  WCHAR CreatedInitiatorName[223 + 1];
} SetInitiatorNodeName_IN, *PSetInitiatorNodeName_IN;
````


## -struct-fields




### -field CreatedInitiatorName

The new initiator name.


## -remarks


It is optional that you implement this class.



## -see-also

<a href="..\iscsiop\ns-iscsiop-_setinitiatornodename_out.md">SetInitiatorNodeName_OUT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565706">SetInitiatorNodeName</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetInitiatorNodeName_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


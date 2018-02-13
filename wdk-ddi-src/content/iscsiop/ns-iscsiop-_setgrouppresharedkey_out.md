---
UID: NS:iscsiop._SetGroupPresharedKey_OUT
title: "_SetGroupPresharedKey_OUT"
author: windows-driver-content
description: The SetGroupPresharedKey_OUT structure holds the output data for the SetGroupPresharedKey method.
old-location: storage\setgrouppresharedkey_out.htm
old-project: storage
ms.assetid: 4ea5e428-783c-4a28-bec5-42106425ee1f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: iscsiop/PSetGroupPresharedKey_OUT, structs-iSCSI_81186f6a-bf08-42eb-a3d8-ae195cdd8135.xml, storage.setgrouppresharedkey_out, *PSetGroupPresharedKey_OUT, PSetGroupPresharedKey_OUT structure pointer [Storage Devices], _SetGroupPresharedKey_OUT, SetGroupPresharedKey_OUT structure [Storage Devices], PSetGroupPresharedKey_OUT, SetGroupPresharedKey_OUT, iscsiop/SetGroupPresharedKey_OUT
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
-	SetGroupPresharedKey_OUT
product: Windows
targetos: Windows
req.typenames: SetGroupPresharedKey_OUT, *PSetGroupPresharedKey_OUT
---

# _SetGroupPresharedKey_OUT structure


## -description


The SetGroupPresharedKey_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565693">SetGroupPresharedKey</a> method.


## -syntax


````
typedef struct _SetGroupPresharedKey_OUT {
  ULONG Status;
} SetGroupPresharedKey_OUT, *PSetGroupPresharedKey_OUT;
````


## -struct-fields




### -field Status

On output, the status of the <b>SetGroupPresharedKey</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>. 


## -remarks



You must implement this method.




## -see-also

<a href="..\iscsiop\ns-iscsiop-_setgrouppresharedkey_in.md">SetGroupPresharedKey_IN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565693">SetGroupPresharedKey</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetGroupPresharedKey_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


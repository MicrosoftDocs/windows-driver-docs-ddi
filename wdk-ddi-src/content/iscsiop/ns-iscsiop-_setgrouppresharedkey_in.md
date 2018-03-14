---
UID: NS:iscsiop._SetGroupPresharedKey_IN
title: "_SetGroupPresharedKey_IN"
author: windows-driver-content
description: The SetGroupPresharedKey_IN structure holds the input data for the SetGroupPresharedKey method.
old-location: storage\setgrouppresharedkey_in.htm
old-project: storage
ms.assetid: fe5e1f75-ebd0-4856-bb77-14efb52fbce0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSetGroupPresharedKey_IN, PSetGroupPresharedKey_IN, PSetGroupPresharedKey_IN structure pointer [Storage Devices], SetGroupPresharedKey_IN, SetGroupPresharedKey_IN structure [Storage Devices], _SetGroupPresharedKey_IN, iscsiop/PSetGroupPresharedKey_IN, iscsiop/SetGroupPresharedKey_IN, storage.setgrouppresharedkey_in, structs-iSCSI_0109dfff-f30e-4f15-ab25-4a290b2fc2f4.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsiop.h
api_name:
-	SetGroupPresharedKey_IN
product: Windows
targetos: Windows
req.typenames: SetGroupPresharedKey_IN, *PSetGroupPresharedKey_IN
---

# _SetGroupPresharedKey_IN structure


## -description


The SetGroupPresharedKey_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565693">SetGroupPresharedKey</a> method.


## -syntax


````
typedef struct _SetGroupPresharedKey_IN {
  ULONG KeySize;
  UCHAR Key[1];
} SetGroupPresharedKey_IN, *PSetGroupPresharedKey_IN;
````


## -struct-fields




### -field KeySize

The size, in bytes, of the key in <b>Key</b><i>.</i>


### -field Key

The preshared group key<i>.</i>


## -remarks



You must implement this method.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565693">SetGroupPresharedKey</a>



<a href="..\iscsiop\ns-iscsiop-_setgrouppresharedkey_out.md">SetGroupPresharedKey_OUT</a>



 

 



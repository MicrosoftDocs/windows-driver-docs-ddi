---
UID: NF:wiautil.wiauPropInPropSpec
title: wiauPropInPropSpec function (wiautil.h)
description: The wiauPropInPropSpec function determines whether a specified property specification ID is contained in an array of such values. The function optionally gets the index at which the property specification ID was found.
old-location: image\wiaupropinpropspec.htm
tech.root: image
ms.assetid: 5ab82378-ff12-46cc-814b-dc533db15a37
ms.date: 05/03/2018
keywords: ["wiauPropInPropSpec function"]
ms.keywords: image.wiaupropinpropspec, wiauFncs_8f694518-d3a5-4636-aae5-046ae519ce0e.xml, wiauPropInPropSpec, wiauPropInPropSpec function [Imaging Devices], wiautil/wiauPropInPropSpec
f1_keywords:
 - "wiautil/wiauPropInPropSpec"
 - "wiauPropInPropSpec"
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wiautil.h
api_name:
- wiauPropInPropSpec
targetos: Windows
req.typenames: 
---

# wiauPropInPropSpec function


## -description


The <b>wiauPropInPropSpec</b> function determines whether a specified property specification ID is contained in an array of such values. The function optionally gets the index at which the property specification ID was found.


## -parameters




### -param NumPropSpecs

Specifies the number of property specification IDs in the array pointed to by <i>pPropSpecs</i>.


### -param pPropSpecs [in]

Points to the first element of the property specification ID array.


### -param PropId

Specifies the property specification ID to search for in the array pointed to by <i>pPropSpecs</i>.


### -param pIdx






#### - pIdx = NULL [out, optional]

<i>Optional</i>. Pointer to a memory location that receives the index of the property specification ID in the property specification ID array. The default value of this parameter is <b>NULL</b>, in which case the function does not use it.


## -returns



This function returns <b>TRUE</b> if it found the property specification ID in the property specification ID array. Otherwise it returns <b>FALSE</b>.




## -remarks



The <b>wiauPropInPropSpec</b> function finds a single property specification ID within an array of property specification IDs. A related function, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaupropsinpropspec">wiauPropsInPropSpec</a> can be used to determine whether any of a specified list of property specification IDs is found in another array of property specification IDs.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaupropsinpropspec">wiauPropsInPropSpec</a>
 

 


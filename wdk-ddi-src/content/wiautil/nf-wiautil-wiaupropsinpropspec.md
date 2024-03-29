---
UID: NF:wiautil.wiauPropsInPropSpec
title: wiauPropsInPropSpec function (wiautil.h)
description: The wiauPropsInPropSpec function determines whether any of a list of property specification IDs is contained within an array of such values.
old-location: image\wiaupropsinpropspec.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["wiauPropsInPropSpec function"]
ms.keywords: image.wiaupropsinpropspec, wiauFncs_2490b5b3-8051-4711-b681-1aef18580182.xml, wiauPropsInPropSpec, wiauPropsInPropSpec function [Imaging Devices], wiautil/wiauPropsInPropSpec
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
targetos: Windows
req.typenames: 
f1_keywords:
 - wiauPropsInPropSpec
 - wiautil/wiauPropsInPropSpec
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiautil.h
api_name:
 - wiauPropsInPropSpec
---

# wiauPropsInPropSpec function


## -description

The <b>wiauPropsInPropSpec</b> function determines whether any of a list of property specification IDs is contained within an array of such values.

## -parameters

### -param NumPropSpecs

Specifies the number of property specification IDs in the array pointed to by the <i>pPropSpecs</i> parameter.

### -param pPropSpecs [in]


Points to the first element of the array of property specification IDs.

### -param NumProps

Specifies the number of property specification IDs to search for.

### -param pProps [in]


Points to the first element of the array containing the property specification IDs to search for.

## -returns

This function returns <b>TRUE</b> as soon as it finds one of the property specification IDs given in the <i>pProps</i> array in the <i>pPropSpecs</i> array. If the function is unable to find any of the listed property specification IDs in that array, it returns <b>FALSE</b>.

## -remarks

The <b>wiauPropsInPropSpec</b> function finds one or more property specification IDs within an array of property specification IDs. A related function, <a href="/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaupropinpropspec">wiauPropInPropSpec</a>, can be used to find a single property specification ID within such an array.

## -see-also

<a href="/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaupropinpropspec">wiauPropInPropSpec</a>

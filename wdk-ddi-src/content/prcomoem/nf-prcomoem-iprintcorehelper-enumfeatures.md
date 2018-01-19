---
UID: NF:prcomoem.IPrintCoreHelper.EnumFeatures
title: IPrintCoreHelper::EnumFeatures method
author: windows-driver-content
description: The IPrintCoreHelper::EnumFeatures method gets a list of all available features, including synthesized and core driver-implement features.
old-location: print\iprintcorehelper_enumfeatures.htm
old-project: print
ms.assetid: 21eddcfe-fe86-4135-a91c-42ec6e8e428a
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintCoreHelper, IPrintCoreHelper::EnumFeatures, EnumFeatures
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintCoreHelper.EnumFeatures
req.alt-loc: Prcomoem.h
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreHelper::EnumFeatures method



## -description
The <b>IPrintCoreHelper::EnumFeatures</b> method gets a list of all available features, including synthesized and core driver-implement features.



## -syntax

````
STDMETHOD EnumFeatures(
  [out] PCSTR *pFeatureList[],
  [out] DWORD *pdwNumFeatures
);
````


## -parameters

### -param pFeatureList[] [out]

A pointer to an array of ANSI character strings that contain all of the features that are available for the current device. The final array element is indicated by a <b>NULL</b> string. The array elements should be considered constants. The caller does not need to provide a buffer for the array, nor should the caller release the array.


### -param pdwNumFeatures [out]

A pointer to a variable that receives the number of feature keywords in the array that is pointed to by the <i>pFeatureList</i> parameter.


## -returns
<b>IPrintCoreHelper::EnumFeatures</b> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.


## -remarks
For Unidrv features, the feature list is based on the GPD view of the configuration file, so features that are surrounded by *<b>Ifdef GDL_ENABLED</b>/*<b>Endif</b> directives are not visible and will not be reported by <b>IPrintCoreHelper::EnumFeatures</b>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552955">IPrintCoreHelper::EnumOptions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelper::EnumFeatures method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


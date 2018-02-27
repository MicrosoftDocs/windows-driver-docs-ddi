---
UID: NF:prcomoem.IPrintCoreHelperUni.EnumFeatures
title: IPrintCoreHelperUni::EnumFeatures method
author: windows-driver-content
description: The IPrintCoreHelperUni::EnumFeatures method gets a list of all available features, including synthesized and core driver-implement features.
old-location: print\iprintcorehelperuni_enumfeatures.htm
old-project: print
ms.assetid: ed21e52b-13a6-4a89-8bbc-9cbf72e3d9fd
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: EnumFeatures method [Print Devices], EnumFeatures method [Print Devices], IPrintCoreHelperUni interface, EnumFeatures,IPrintCoreHelperUni.EnumFeatures, IPrintCoreHelperUni, IPrintCoreHelperUni interface [Print Devices], EnumFeatures method, IPrintCoreHelperUni::EnumFeatures, prcomoem/IPrintCoreHelperUni::EnumFeatures, print.iprintcorehelperuni_enumfeatures, print_unidrv-pscript_allplugins_a41557cd-962d-4b7c-960d-dd213b1a68e2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: 
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Prcomoem.h
api_name:
-	IPrintCoreHelperUni.EnumFeatures
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreHelperUni::EnumFeatures method


## -description


The <code>IPrintCoreHelperUni::EnumFeatures</code> method gets a list of all available features, including synthesized and core driver-implement features.


## -syntax


````
STDMETHOD EnumFeatures(
  [out] PCSTR *pFeatureList[],
  [out] DWORD *pdwNumFeatures
);
````


## -parameters




### -param pFeatureList




### -param pdwNumFeatures [out]

A pointer to a variable that receives the number of feature keywords in the array that is pointed to by the <i>pFeatureList</i> parameter.


#### - pFeatureList[] [out]

A pointer to an array of ANSI character strings that contain all of the features that are available for the current device. The final array element is indicated by a <b>NULL</b> string.


## -returns



<code>IPrintCoreHelperUni::EnumFeatures</code> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.




## -remarks



For Unidrv features, the feature list is based on the GPD view of the configuration file, so features that are surrounded by "*Ifdef GDL_ENABLED/*Endif" directives cannot be configured by using this method.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552934">IPrintCoreHelperUni::EnumOptions</a>



<a href="..\prcomoem\nn-prcomoem-iprintcorehelperuni.md">IPrintCoreHelperUni</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelperUni::EnumFeatures method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


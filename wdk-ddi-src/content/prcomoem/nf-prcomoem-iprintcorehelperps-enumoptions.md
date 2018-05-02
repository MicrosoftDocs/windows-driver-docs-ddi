---
UID: NF:prcomoem.IPrintCoreHelperPS.EnumOptions
title: IPrintCoreHelperPS::EnumOptions
author: windows-driver-content
description: The IPrintCoreHelperPS::EnumOptions method gets a list of available options for the given feature.
old-location: print\iprintcorehelperps_enumoptions.htm
old-project: print
ms.assetid: bd23f4e6-7a99-4347-ae29-a1e832db2e03
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: EnumOptions, EnumOptions method [Print Devices], EnumOptions method [Print Devices],IPrintCoreHelperPS interface, IPrintCoreHelperPS interface [Print Devices],EnumOptions method, IPrintCoreHelperPS.EnumOptions, IPrintCoreHelperPS::EnumOptions, prcomoem/IPrintCoreHelperPS::EnumOptions, print.iprintcorehelperps_enumoptions, print_unidrv-pscript_allplugins_89c5ea61-aedf-43c6-9a8b-020656476f35.xml
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
-	COM
api_location:
-	Prcomoem.h
api_name:
-	IPrintCoreHelperPS.EnumOptions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelperPS::EnumOptions


## -description


The <b>IPrintCoreHelperPS::EnumOptions</b> method gets a list of available options for the given feature. 


## -parameters




### -param pszFeatureKeyword [in]

An ANSI character string that contains the feature whose options are requested. 


### -param pOptionList




### -param pdwNumOptions [out]

A pointer to a variable that receives the number of options in the option array that is pointed to by the <i>pOptionList</i> parameter.


#### - pOptionList[] [out]

A pointer to an array of ANSI character strings that contain all of the options for the feature that is specified in the <i>pszFeatureKeyword</i> parameter. <b>IPrintCoreHelperPS::EnumOptions</b> is responsible for allocating the memory for the array. The last element of the array must be a <b>NULL</b> string.


## -returns



<b>IPrintCoreHelperPS::EnumOptions</b> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.




## -remarks



When <b>IPrintCoreHelperPS::EnumOptions</b> returns, the option list contains all options, regardless of constraints or other factors.




## -see-also




<a href="https://msdn.microsoft.com/2be594f1-1eb1-42e0-a345-ee7edf4d96dd">IPrintCoreHelperPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551972">IPrintCoreHelperPS::EnumConstrainedOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551977">IPrintCoreHelperPS::EnumFeatures</a>
 

 


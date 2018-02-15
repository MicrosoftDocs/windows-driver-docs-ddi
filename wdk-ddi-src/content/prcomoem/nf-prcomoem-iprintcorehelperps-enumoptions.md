---
UID: NF:prcomoem.IPrintCoreHelperPS.EnumOptions
title: IPrintCoreHelperPS::EnumOptions method
author: windows-driver-content
description: The IPrintCoreHelperPS::EnumOptions method gets a list of available options for the given feature.
old-location: print\iprintcorehelperps_enumoptions.htm
old-project: print
ms.assetid: bd23f4e6-7a99-4347-ae29-a1e832db2e03
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.iprintcorehelperps_enumoptions, IPrintCoreHelperPS interface [Print Devices], EnumOptions method, EnumOptions, EnumOptions method [Print Devices], IPrintCoreHelperPS interface, prcomoem/IPrintCoreHelperPS::EnumOptions, EnumOptions method [Print Devices], IPrintCoreHelperPS::EnumOptions, print_unidrv-pscript_allplugins_89c5ea61-aedf-43c6-9a8b-020656476f35.xml, IPrintCoreHelperPS
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Prcomoem.h
apiname:
-	IPrintCoreHelperPS.EnumOptions
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreHelperPS::EnumOptions method


## -description


The <b>IPrintCoreHelperPS::EnumOptions</b> method gets a list of available options for the given feature. 


## -syntax


````
STDMETHOD EnumOptions(
  [in]  PCSTR pszFeatureKeyword,
  [out] PCSTR *pOptionList[],
  [out] DWORD *pdwNumOptions
);
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551977">IPrintCoreHelperPS::EnumFeatures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551972">IPrintCoreHelperPS::EnumConstrainedOptions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelperPS::EnumOptions method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


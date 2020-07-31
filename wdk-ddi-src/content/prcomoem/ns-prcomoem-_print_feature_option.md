---
UID: NS:prcomoem._PRINT_FEATURE_OPTION
title: _PRINT_FEATURE_OPTION (prcomoem.h)
description: The PRINT_FEATURE_OPTION structure contains information about a feature-option pair, where the option is one option of a particular feature.
old-location: print\print_feature_option.htm
tech.root: print
ms.assetid: 82c9c54b-f124-46d7-a3c9-a17fd8028412
ms.date: 04/20/2018
keywords: ["_PRINT_FEATURE_OPTION structure"]
ms.keywords: PRINT_FEATURE_OPTION, PRINT_FEATURE_OPTION structure [Print Devices], _PRINT_FEATURE_OPTION, prcomoem/PRINT_FEATURE_OPTION, print.print_feature_option, print_unidrv-pscript_ui_2f776943-da30-40c4-909a-56472768c8df.xml
f1_keywords:
 - "prcomoem/PRINT_FEATURE_OPTION"
 - "PRINT_FEATURE_OPTION"
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- prcomoem.h
api_name:
- PRINT_FEATURE_OPTION
targetos: Windows
req.typenames: PRINT_FEATURE_OPTION
---

# _PRINT_FEATURE_OPTION structure


## -description


The PRINT_FEATURE_OPTION structure contains information about a feature-option pair, where the option is one option of a particular feature.


## -struct-fields




### -field pszFeature

The printing feature.


### -field pszOption

One of the options for the printing feature.


## -remarks



This structure is used by methods that belong to the <b>IPrintCoreHelper</b>, <b>IPrintCoreHelperPS</b>, and <b>IPrintCoreHelperUni</b> interfaces. The methods are listed in the See Also section.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelper-setoptions">IPrintCoreHelper::SetOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelper-whyconstrained">IPrintCoreHelper::WhyConstrained</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperps-setoptions">IPrintCoreHelperPS::SetOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperps-whyconstrained">IPrintCoreHelperPS::WhyConstrained</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperuni-setoptions">IPrintCoreHelperUni::SetOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperuni-whyconstrained">IPrintCoreHelperUni::WhyConstrained</a>
 

 


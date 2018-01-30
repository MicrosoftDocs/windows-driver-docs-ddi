---
UID: NS:prcomoem._PRINT_FEATURE_OPTION
title: "_PRINT_FEATURE_OPTION"
author: windows-driver-content
description: The PRINT_FEATURE_OPTION structure contains information about a feature-option pair, where the option is one option of a particular feature.
old-location: print\print_feature_option.htm
old-project: print
ms.assetid: 82c9c54b-f124-46d7-a3c9-a17fd8028412
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.print_feature_option, print_unidrv-pscript_ui_2f776943-da30-40c4-909a-56472768c8df.xml, PRINT_FEATURE_OPTION structure [Print Devices], _PRINT_FEATURE_OPTION, prcomoem/PRINT_FEATURE_OPTION, PRINT_FEATURE_OPTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	prcomoem.h
apiname:
-	PRINT_FEATURE_OPTION
product: Windows
targetos: Windows
req.typenames: PRINT_FEATURE_OPTION
req.product: Windows 10 or later.
---

# _PRINT_FEATURE_OPTION structure


## -description


The PRINT_FEATURE_OPTION structure contains information about a feature-option pair, where the option is one option of a particular feature.


## -syntax


````
typedef struct _PRINT_FEATURE_OPTION {
  PCSTR pszFeature;
  PCSTR pszOption;
} PRINT_FEATURE_OPTION;
````


## -struct-fields




### -field pszFeature

The printing feature.


### -field pszOption

One of the options for the printing feature.


## -remarks


This structure is used by methods that belong to the <b>IPrintCoreHelper</b>, <b>IPrintCoreHelperPS</b>, and <b>IPrintCoreHelperUni</b> interfaces. The methods are listed in the See Also section.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552915">IPrintCoreHelperPS::WhyConstrained</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552963">IPrintCoreHelper::SetOptions</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552965">IPrintCoreHelper::WhyConstrained</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552912">IPrintCoreHelperPS::SetOptions</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552947">IPrintCoreHelperUni::WhyConstrained</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552945">IPrintCoreHelperUni::SetOptions</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20PRINT_FEATURE_OPTION structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


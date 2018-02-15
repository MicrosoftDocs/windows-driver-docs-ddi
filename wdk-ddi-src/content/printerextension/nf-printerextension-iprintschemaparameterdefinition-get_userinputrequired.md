---
UID: NF:printerextension.IPrintSchemaParameterDefinition.get_UserInputRequired
title: IPrintSchemaParameterDefinition::get_UserInputRequired method
author: windows-driver-content
description: The UserInputRequired property gets the Boolean value that indicates whether or not a user input value is required for the Print Schema parameter.
old-location: print\_iprintschemaparameterdefinition_userinputrequired.htm
old-project: print
ms.assetid: C2BA76C4-CCFB-4F0B-B5DC-3A35BD5A3884
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: UserInputRequired property [Print Devices], IPrintSchemaParameterDefinition interface, IPrintSchemaParameterDefinition, get_UserInputRequired, IPrintSchemaParameterDefinition::get_UserInputRequired, printerextension/IPrintSchemaParameterDefinition::UserInputRequired, printerextension/IPrintSchemaParameterDefinition::get_UserInputRequired, IPrintSchemaParameterDefinition.UserInputRequired, print._iprintschemaparameterdefinition_userinputrequired, IPrintSchemaParameterDefinition interface [Print Devices], UserInputRequired property, UserInputRequired property [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrintSchemaParameterDefinition.UserInputRequired
-	IPrintSchemaParameterDefinition.get_UserInputRequired
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaParameterDefinition::get_UserInputRequired method


## -description


The <b>UserInputRequired</b> property gets the Boolean value that indicates whether or not a user input value is required for the Print Schema parameter.

This property is read-only.


## -syntax


````
HRESULT get_UserInputRequired(
  [out, retval] BOOL *pbIsRequired
);
````


## -parameters


## -remarks



The print dialog can use <b>UserInputRequired</b> to determine whether or not it should force the user to enter a valid value for the parameter, before it allows printing to proceed.




## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemaparameterdefinition.md">IPrintSchemaParameterDefinition</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaParameterDefinition::UserInputRequired property%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


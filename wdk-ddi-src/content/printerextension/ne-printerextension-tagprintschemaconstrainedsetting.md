---
UID: NE:printerextension.tagPrintSchemaConstrainedSetting
title: tagPrintSchemaConstrainedSetting
author: windows-driver-content
description: The PrintSchemaConstrainedSetting enumeration specifies whether the Option is available based on the current device configuration. The constrained attribute appears only in a PrintCapabilities document.
old-location: print\printschemaconstrainedsetting.htm
old-project: print
ms.assetid: 637A210F-9FD7-49BD-AF71-8A77E07D5C20
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: PrintSchemaConstrainedSetting, PrintSchemaConstrainedSetting_Admin, printerextension/PrintSchemaConstrainedSetting_Admin, print.printschemaconstrainedsetting, PrintSchemaConstrainedSetting_PrintTicket, PrintSchemaConstrainedSetting_None, printerextension/PrintSchemaConstrainedSetting_Device, PrintSchemaConstrainedSetting_Device, printerextension/PrintSchemaConstrainedSetting, PrintSchemaConstrainedSetting enumeration [Print Devices], tagPrintSchemaConstrainedSetting, printerextension/PrintSchemaConstrainedSetting_None, printerextension/PrintSchemaConstrainedSetting_PrintTicket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Printerextension.h
apiname:
-	PrintSchemaConstrainedSetting
product: Windows
targetos: Windows
req.typenames: PrintSchemaConstrainedSetting
req.product: Windows 10 or later.
---

# tagPrintSchemaConstrainedSetting enumeration


## -description


The  PrintSchemaConstrainedSetting enumeration specifies whether the Option is available based on the current device configuration. The <b>constrained</b> attribute appears only in a PrintCapabilities document.


## -syntax


````
typedef enum tagPrintSchemaConstrainedSetting { 
  PrintSchemaConstrainedSetting_None         = 0,
  PrintSchemaConstrainedSetting_PrintTicket  = 1,
  PrintSchemaConstrainedSetting_Admin        = 2,
  PrintSchemaConstrainedSetting_Device       = 3
} PrintSchemaConstrainedSetting;
````


## -enum-fields




### -field PrintSchemaConstrainedSetting_None

The Option is not constrained.


### -field PrintSchemaConstrainedSetting_PrintTicket

The Option is constrained by the PrintTicket settings. Changing the PrintTicket document settings should be able to remove the constraint.


### -field PrintSchemaConstrainedSetting_Admin

The Option is constrained by the administrator's settings. The Option constraint should not be removable by a user without administrator privileges.


### -field PrintSchemaConstrainedSetting_Device

The Option is constrained by the device configuration. The Option should not be removable by either a user or administrator without changing the device configuration.


## -see-also

<a href="https://msdn.microsoft.com/57E13395-9E23-4708-B4EC-6839CB6FC62B">IPrintSchemaOption::Constrained</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20PrintSchemaConstrainedSetting enumeration%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


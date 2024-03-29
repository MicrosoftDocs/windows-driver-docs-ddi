---
UID: NS:winsplp.SHOWUIPARAMS
title: SHOWUIPARAMS (winsplp.h)
description: The SplPromptUIInUsersSession function uses the SHOWUIPARAMS structure to hold information about the appearance and behavior of a message box.
old-location: print\showuiparams.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["SHOWUIPARAMS structure"]
ms.keywords: "*PSHOWUIPARAMS, PSHOWUIPARAMS, PSHOWUIPARAMS structure pointer [Print Devices], SHOWUIPARAMS, SHOWUIPARAMS structure [Print Devices], print.showuiparams, spoolfnc_bf6ce7c8-8b86-40c9-9b03-64c3e3366a04.xml, winsplp/PSHOWUIPARAMS, winsplp/SHOWUIPARAMS"
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Windows
req.target-min-winverclnt: This function is available in Windows XP and later operating systems.
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
req.typenames: SHOWUIPARAMS, *PSHOWUIPARAMS
f1_keywords:
 - PSHOWUIPARAMS
 - winsplp/PSHOWUIPARAMS
 - SHOWUIPARAMS
 - winsplp/SHOWUIPARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winsplp.h
api_name:
 - PSHOWUIPARAMS
 - SHOWUIPARAMS
---

# SHOWUIPARAMS structure


## -description

The <a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-splpromptuiinuserssession">SplPromptUIInUsersSession</a> function uses the SHOWUIPARAMS structure to hold information about the appearance and behavior of a message box.

## -struct-fields

### -field UIType

Specifies the type of user interface element. This member can be set to a single value: <b>kMessageBox</b>.

### -field MessageBoxParams

Specifies a <a href="/windows-hardware/drivers/ddi/winsplp/ns-winsplp-messagebox_params">MESSAGEBOX_PARAMS</a> structure that contains the information about the message box.

## -see-also

<a href="/windows-hardware/drivers/ddi/winsplp/ns-winsplp-messagebox_params">MESSAGEBOX_PARAMS</a>



<a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-splpromptuiinuserssession">SplPromptUIInUsersSession</a>


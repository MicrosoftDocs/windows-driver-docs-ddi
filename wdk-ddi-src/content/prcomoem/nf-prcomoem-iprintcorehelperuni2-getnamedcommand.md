---
UID: NF:prcomoem.IPrintCoreHelperUni2.GetNamedCommand
title: IPrintCoreHelperUni2::GetNamedCommand (prcomoem.h)
description: The GetNamedCommand method returns the specified command.
old-location: print\iprintcorehelperuni2_getnamedcommand.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintCoreHelperUni2::GetNamedCommand"]
ms.keywords: GetNamedCommand, GetNamedCommand method [Print Devices], GetNamedCommand method [Print Devices],IPrintCoreHelperUni2 interface, IPrintCoreHelperUni2 interface [Print Devices],GetNamedCommand method, IPrintCoreHelperUni2.GetNamedCommand, IPrintCoreHelperUni2::GetNamedCommand, prcomoem/IPrintCoreHelperUni2::GetNamedCommand, print.iprintcorehelperuni2_getnamedcommand
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintCoreHelperUni2::GetNamedCommand
 - prcomoem/IPrintCoreHelperUni2::GetNamedCommand
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintCoreHelperUni2.GetNamedCommand
---

# IPrintCoreHelperUni2::GetNamedCommand


## -description

The <b>GetNamedCommand</b> method returns the specified command.

## -parameters

### -param pDevmode 

[in]
A pointer to a DEVMODE structure.

### -param cbSize 

[in]
The number of bytes in <i>pDevmode</i>, not the number of bytes written.

### -param pszCommandName 

[in]
The command name. This parameter accepts standard command names from the GPD, except for those that require an *Order attribute. Those six sections of ordered command sequences are accessible via the following special command names:

<ul>
<li>L"SectionJobSetup"</li>
<li>L"SectionDocSetup"</li>
<li>L"SectionPageSetup"</li>
<li>L"SectionPageFinish"</li>
<li>L"SectionDocFinish"</li>
<li>L"SectionJobFinish"</li>
</ul>

### -param ppCommandBytes 

[out]
The output buffer. This buffer does not need to be freed by the caller.

### -param pcbCommandSize 

[out]
The size of the output buffer.

## -returns

This method returns an <b>HRESULT</b> value.

## -remarks

The <b>GetNamedCommand</b> method will not return commands containing references to Standard Variables.

## -see-also

<a href="/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelperuni2">IPrintCoreHelperUni2</a>

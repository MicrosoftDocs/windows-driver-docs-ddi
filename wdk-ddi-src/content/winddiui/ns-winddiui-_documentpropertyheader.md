---
UID: NS:winddiui._DOCUMENTPROPERTYHEADER
title: "_DOCUMENTPROPERTYHEADER"
author: windows-driver-content
description: The DOCUMENTPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's DrvDocumentPropertySheets function.
old-location: print\documentpropertyheader.htm
old-project: print
ms.assetid: 5aaf1f90-fb75-4e5a-9316-9212a21b8fed
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDOCUMENTPROPERTYHEADER, DOCUMENTPROPERTYHEADER, DOCUMENTPROPERTYHEADER structure [Print Devices], PDOCUMENTPROPERTYHEADER, PDOCUMENTPROPERTYHEADER structure pointer [Print Devices], _DOCUMENTPROPERTYHEADER, print.documentpropertyheader, print_interface-graphics_d12da62c-2384-4bc3-a83d-ed948460d718.xml, winddiui/DOCUMENTPROPERTYHEADER, winddiui/PDOCUMENTPROPERTYHEADER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winddiui.h
req.include-header: Winddiui.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winddiui.h
api_name:
-	DOCUMENTPROPERTYHEADER
product: Windows
targetos: Windows
req.typenames: DOCUMENTPROPERTYHEADER, *PDOCUMENTPROPERTYHEADER
req.product: Windows 10 or later.
---

# _DOCUMENTPROPERTYHEADER structure


## -description


The DOCUMENTPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's <a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a> function.


## -struct-fields




### -field cbSize

Size, in bytes, of the DOCUMENTPROPERTYHEADER structure.


### -field Reserved

Reserved. Must be zero.


### -field hPrinter

Printer handle.


### -field pszPrinterName

Pointer to a NULL-terminated string representing the printer's name.


### -field pdmIn

Pointer to an input <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a> function should copy into the printer interface DLL's internal DEVMODEW structure (before the property sheet is displayed, if applicable). If DM_IN_BUFFER or DM_MODIFY is not set in <b>fMode</b>, this pointer is <b>NULL</b>.


### -field pdmOut

Pointer to an output DEVMODEW structure into which the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a> function should copy the printer interface DLL's internal DEVMODEW contents (after the property sheet has been displayed, if applicable). If DM_OUT_BUFFER or DM_COPY is not set in <b>fMode</b>, this pointer is <b>NULL</b>.


### -field cbOut

Specifies the size, in bytes, of the buffer to which <b>pdmOut</b> points. For more information, see the following Remarks section.


### -field fMode

One or more of the bit flags listed in the following table. (The flags are defined in header files Wingdi.h and Winddiui.h.)

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
No flags set (that is, <b>fMode</b> is 0).

</td>
<td>
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a> function should return the size, in bytes, of its DEVMODEW structure, including all public and private members, in the <b>cbOut</b> member.

</td>
</tr>
<tr>
<td>
DM_ADVANCED

</td>
<td>
If set, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a> function should only create the Advanced document page.

If not set, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a> function should create both the PageSetup and Advanced document pages.

(See the description of the <b>pDlgPage</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546211">COMPROPSHEETUI</a> structure.)

</td>
</tr>
<tr>
<td>
DM_IN_BUFFER or

DM_MODIFY

</td>
<td>
The caller has supplied a DEVMODEW structure pointer in <b>pdmIn</b>, and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a> function should update its internal DEVMODEW structure to reflect the contents of the supplied DEVMODEW.

</td>
</tr>
<tr>
<td>
DM_IN_PROMPT or

DM_PROMPT

</td>
<td>
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a> function should create its property sheet pages.

(This flag is never set if the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a> function's <i>pPSUIInfo</i> parameter is <b>NULL</b>.)

</td>
</tr>
<tr>
<td>
DM_NOPERMISSION

</td>
<td>
The printer interface DLL's <a href="https://msdn.microsoft.com/library/windows/hardware/ff564313">_CPSUICALLBACK</a>-typed callback should not allow the user to modify properties on the displayed property sheet pages.

</td>
</tr>
<tr>
<td>
DM_OUT_BUFFER or

DM_COPY

</td>
<td>
The caller has supplied a DEVMODEW structure pointer in <b>pdmOut</b>, and the <a href="https://msdn.microsoft.com/fc7e98ba-5c49-4c2d-af2e-b6c13757f6e6">DrvDocumentPropertySheets </a>function should copy the contents of its internal DEVMODEW structure into the supplied DEVMODEW.

</td>
</tr>
<tr>
<td>
DM_PROMPT_NON_MODAL

</td>
<td>
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a> function should create its property sheet pages, and launch a non-modal UI.

(This flag is never set if the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a> function's <i>pPSUIInfo</i> parameter is <b>NULL</b>.)

</td>
</tr>
<tr>
<td>
DM_USER_DEFAULT

</td>
<td>
Not used.

</td>
</tr>
<tr>
<td>
DM_OUT_DEFAULT or

DM_UPDATE

</td>
<td>
Not used.

</td>
</tr>
</table>
 


## -remarks



The input value in the <b>cbOut</b> member is not necessarily equal to the size of the buffer pointed to by the <b>pdmOut</b> member. For example, when the <i>pPSUInfo</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a> function is <b>NULL</b>, and if either the <b>fMode</b> member of the DOCUMENTPROPERTYHEADER structure is zero, or the <b>pdmOut</b> member of the same structure is <b>NULL</b>, a driver should write the total size of the printer's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure (including the public and private structure members) in the <b>cbOut</b> member. In such a case, a driver should treat the <b>cbOut</b> member as a "write-only" member. The "plotter" sample that ships with the Windows Driver Kit (WDK) demonstrates how to use the <b>cbOut</b> member correctly.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546211">COMPROPSHEETUI</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DOCUMENTPROPERTYHEADER structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


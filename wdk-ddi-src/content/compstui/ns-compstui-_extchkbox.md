---
UID: NS:compstui._EXTCHKBOX
title: _EXTCHKBOX
author: windows-driver-content
description: The EXTCHKBOX structure is used by CPSUI applications (including printer interface DLLs) for specifying an extended check box, which can be added to a property sheet page option.
old-location: print\extchkbox.htm
old-project: print
ms.assetid: b3b82474-d4e5-467c-93dc-30edac189c66
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _EXTCHKBOX, *PEXTCHKBOX, EXTCHKBOX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: compstui.h
req.include-header: Compstui.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EXTCHKBOX
req.alt-loc: compstui.h
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
req.typenames: *PEXTCHKBOX, EXTCHKBOX
---

# _EXTCHKBOX structure



## -description
The EXTCHKBOX structure is used by CPSUI applications (including printer interface DLLs) for specifying an extended check box, which can be added to a property sheet page option.



## -syntax

````
typedef struct _EXTCHKBOX {
  WORD      cbSize;
  WORD      Flags;
  LPTSTR    pTitle;
  LPTSTR    pSeparator;
  LPTSTR    pCheckedName;
  ULONG_PTR IconID;
  WORD      wReserved[4];
  ULONG_PTR dwReserved[2];
} EXTCHKBOX, *PEXTCHKBOX;
````


## -struct-fields

### -field cbSize

Size, in bytes, of the EXTCHKBOX structure.


### -field Flags

Bit flags, which can be one of the following:




### -field ECBF_CHECKNAME_AT_FRONT

If set, CPSUI displays strings in the order "pCheckedName pSeparator <i>SelectName</i>", where <i>SelectName</i> is the string associated with the option's selected value.

If not set, CPSUI displays strings in the order "<i>SelectName</i> pSeparator pCheckedName".

</dd>
</dl>



### -field ECBF_CHECKNAME_ONLY_ENABLED

If set, CPSUI displays the pCheckedName string only if the option is checked and enabled (that is, OPTIF_ECB_CHECKED is set and OPTIF_DISABLED is clear in the OPTITEM structure).

If not set, CPSUI always displays the pCheckedName string if the option is checked (that is, OPTIF_ECB_CHECKED is set in the OPTITEM structure), even if the option is disabled.

</dd>
</dl>



### -field ECBF_ICONID_AS_HICON

If set, the <b>IconID</b> member contains an icon handle.

If not set, the <b>IconID</b> member contains an icon resource identifier.

</dd>
</dl>



### -field ECBF_OVERLAY_ECBICON_IF_CHECKED

If set, and if the check box is checked (that is, OPTIF_ECB_CHECKED is set in the OPTITEM structure), CPSUI overlays the icon identified by the <b>IconID</b> member onto the icon associated with the option item.

</dd>
</dl>



### -field ECBF_OVERLAY_NO_ICON

If set, CPSUI overlays its IDI_CPSUI_NO icon onto the icon identified by the <b>IconID</b> member.

</dd>
</dl>



### -field ECBF_OVERLAY_STOP_ICON

If set, CPSUI overlays the IDI_CPSUI_STOP icon onto the icon identified by the <b>IconID</b> member.

</dd>
</dl>



### -field ECBF_OVERLAY_WARNING_ICON

If set, CPSUI overlays its IDI_CPSUI_WARNING icon onto the icon identified by the <b>IconID</b> member.

</dd>
</dl>

### -field pTitle

String identifier, representing the check box title. This can be a 32-bit pointer to a NULL-terminated string, or it can be a 16-bit string resource identifier with HIWORD set to zero.


### -field pSeparator

String identifier, representing a separator character to be displayed between the checked name string and the selected option string This can be a 32-bit pointer to a NULL-terminated string, or it can be a 16-bit string resource identifier with HIWORD set to zero.


### -field pCheckedName

String identifier, representing the text to be displayed when the check box is checked. This can be a 32-bit pointer to a NULL-terminated string, or it can be a 16-bit string resource identifier with HIWORD set to zero.


### -field IconID

One of the following icon identifiers:

<ul>
<li>
An icon resource identifier. This can be application-defined, or it can be one of the CPSUI-supplied, IDI_CPSUI-prefixed icon resource identifiers.

</li>
<li>
An icon handle. If a handle is specified, ECBF_ICONID_AS_HICON must be set in the <b>Flags</b> member.

</li>
</ul>
If this value is zero, an icon is not displayed.


### -field wReserved

Reserved, must be initialized to zero.


### -field dwReserved

Reserved, must be initialized to zero.


## -remarks
An extended check box is a CPSUI-defined type of check box that can be associated with an <a href="..\compstui\ns-compstui-_optitem.md">OPTITEM</a> structure. An OPTITEM structure can have one extended check box or one extended push button associated with it.


## -see-also
<dl>
<dt>
<a href="..\compstui\ns-compstui-_extpush.md">EXTPUSH</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20EXTCHKBOX structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


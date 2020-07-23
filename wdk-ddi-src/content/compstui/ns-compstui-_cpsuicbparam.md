---
UID: NS:compstui._CPSUICBPARAM
title: _CPSUICBPARAM (compstui.h)
description: The CPSUICBPARAM structure is used as the input parameter to _CPSUICALLBACK-typed callback functions.
old-location: print\cpsuicbparam.htm
tech.root: print
ms.assetid: b5545efa-6cb4-41d0-9338-be9a269fa193
ms.date: 04/20/2018
keywords: ["_CPSUICBPARAM structure"]
ms.keywords: "*PCPSUICBPARAM, CPSUICBPARAM, CPSUICBPARAM structure [Print Devices], PCPSUICBPARAM, PCPSUICBPARAM structure pointer [Print Devices], _CPSUICBPARAM, compstui/CPSUICBPARAM, compstui/PCPSUICBPARAM, cpsuifnc_9e2d49ae-ecb6-4979-aacd-7dd954034e92.xml, print.cpsuicbparam"
f1_keywords:
 - "compstui/CPSUICBPARAM"
 - "CPSUICBPARAM"
req.header: compstui.h
req.include-header: Compstui.h
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
- compstui.h
api_name:
- CPSUICBPARAM
targetos: Windows
req.typenames: CPSUICBPARAM, *PCPSUICBPARAM
---

# _CPSUICBPARAM structure


## -description


The CPSUICBPARAM structure is used as the input parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-_cpsuicallback">_CPSUICALLBACK</a>-typed callback functions.


## -struct-fields




### -field cbSize

CPSUI-supplied size, in bytes, of the CPSUICBPARAM structure.


### -field Reason

CPSUI-supplied value indicating the reason it is calling the callback function. This can be one of the following values:





#### CPSUICB_REASON_ABOUT

The user has clicked on the page's <b>About</b> button, and the application previously set the CPSUIF_ABOUT_CALLBACK flag in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui">COMPROPSHEETUI</a> structure. CPSUI sets <i>pCurItem</i> to the value contained in <b>pOptItem</b>, and sets <b>pOldSel</b> to point to the <b>COMPROPSHEETUI</b> structure.





#### CPSUICB_REASON_APPLYNOW

The user has clicked on the page's <b>Apply</b> or <b>OK</b> button, and CPSUI has received a PSN_APPLY notification message (described in the Microsoft Windows SDK documentation). CPSUI sets <b>pCurItem</b> to point to the option to which <b>pOptItem</b> points. It also sets <b>OldSel</b> to minus one to indicate that all valid changed option values should be applied now.





#### CPSUICB_REASON_DLGPROC

The option identified by <b>pCurItem</b> is a push button (<a href="https://docs.microsoft.com/windows-hardware/drivers/print/tvot-pushbutton">TVOT_PUSHBUTTON</a> option type), and the user has clicked on the button.

The push button option's OPTPARAM <b>Style</b> field is set to PUSHBUTTON_TYPE_DLGPROC.





#### CPSUICB_REASON_ECB_CHANGED

The option identified by <b>pCurItem</b> is an extended check box, and the user has changed the box's state.





#### CPSUICB_REASON_EXTPUSH

The option identified by <b>pCurItem</b> is an extended push button, and the user has clicked on the button.





#### CPSUICB_REASON_ITEMS_REVERTED

The user clicked on the page's <b>Undo</b> button, and CPSUI has reverted all selections to their original values.





#### CPSUICB_REASON_KILLACTIVE

The property sheet page is about to lose activation, and CPSUI has received a PSN_KILLACTIVE notification message (described in the Windows SDK documentation). CPSUI sets <b>pCurItem</b> to the value contained in <b>pOptItem</b>, and sets <b>pOldSel</b> to point to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui">COMPROPSHEETUI</a> structure.





#### CPSUICB_REASON_OPTITEM_SETFOCUS

The option identified by <b>pCurItem</b> has received input focus.





#### CPSUICB_REASON_PUSHBUTTON

The option identified by <b>pCurItem</b> is a push button (<a href="https://docs.microsoft.com/windows-hardware/drivers/print/tvot-pushbutton">TVOT_PUSHBUTTON</a> option type), and the user has clicked on the button.

The push button item's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_optparam">OPTPARAM</a> <b>Style</b>  field is set to PUSHBUTTON_TYPE_CALLBACK.





#### CPSUICB_REASON_SEL_CHANGED

The user has changed the selected value for the option pointed to by <b>pCurItem</b>.





#### CPSUICB_REASON_SETACTIVE

The property sheet page is about to become active, and CPSUI has received a PSN_SETACTIVE notification message (described in the Windows SDK documentation). CPSUI sets <b>pCurItem</b> to the value contained in <b>pOptItem</b>, and sets <b>pOldSel</b> to point to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui">COMPROPSHEETUI</a> structure.


### -field hDlg

CPSUI-supplied handle to the currently active dialog box.


### -field pOptItem

CPSUI-supplied pointer to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_optitem">OPTITEM</a> structures. This is the same pointer that the application previously supplied in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui">COMPROPSHEETUI</a> structure.


### -field cOptItem

CPSUI-supplied number of OPTITEM structures in the array pointed to by <b>pOptItem</b>. This is the same number that the application previously supplied in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui">COMPROPSHEETUI</a> structure.


### -field Flags

CPSUI-supplied flags. This is the same set of flags that the application previously supplied in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui">COMPROPSHEETUI</a> structure.


### -field pCurItem

CPSUI-supplied pointer to a member of the OPTITEM array pointed to by <b>pOptItem</b>. This array member represents the "current" option, which is the one for which the callback function was called.


### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.OldSel

If the <b>Reason</b> member contains CPSUICB_REASON_SEL_CHANGED, CPSUI sets this union to the previous contents of the <b>OldSel</b>/<b>pOldSel</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_optitem">OPTITEM</a> structure pointed to by <b>pCurItem</b>.

For all other <b>Reason</b> values, the contents of this union should be ignored.


### -field DUMMYUNIONNAME.pOldSel

If the <b>Reason</b> member contains CPSUICB_REASON_SEL_CHANGED, CPSUI sets this union to the previous contents of the <b>OldSel</b>/<b>pOldSel</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_optitem">OPTITEM</a> structure pointed to by <b>pCurItem</b>.

For all other <b>Reason</b> values, the contents of this union should be ignored.


### -field UserData

CPSUI-supplied user data. This is the same value that the application previously supplied in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui">COMPROPSHEETUI</a> structure.


### -field Result

Result value supplied by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-_cpsuicallback">_CPSUICALLBACK</a>-typed callback function. By default, CPSUI sets this value to CPSUI_OK. After the callback function returns, CPSUI calls its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> function with a function code of <a href="https://docs.microsoft.com/previous-versions/ff547087(v=vs.85)">CPSFUNC_SET_RESULT</a>, supplying the <b>Reason</b> member contents as the result value.

This member is used only if the <b>Reason</b> member is CPSUICB_REASON_APPLYNOW and the callback function does not return CPSUI_ACTION_NO_APPLY_EXIT.


---
UID: NS:compstui._CPSUICBPARAM
title: CPSUICBPARAM (compstui.h)
description: The CPSUICBPARAM structure is used as the input parameter to _CPSUICALLBACK-typed callback functions.
tech.root: print
ms.date: 11/15/2022
keywords: ["CPSUICBPARAM structure"]
ms.keywords: "*PCPSUICBPARAM, CPSUICBPARAM, CPSUICBPARAM structure [Print Devices], PCPSUICBPARAM, PCPSUICBPARAM structure pointer [Print Devices], _CPSUICBPARAM, compstui/CPSUICBPARAM, compstui/PCPSUICBPARAM, cpsuifnc_9e2d49ae-ecb6-4979-aacd-7dd954034e92.xml, print.cpsuicbparam"
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
targetos: Windows
req.typenames: CPSUICBPARAM, *PCPSUICBPARAM
f1_keywords:
 - _CPSUICBPARAM
 - compstui/_CPSUICBPARAM
 - PCPSUICBPARAM
 - compstui/PCPSUICBPARAM
 - CPSUICBPARAM
 - compstui/CPSUICBPARAM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - compstui.h
api_name:
 - _CPSUICBPARAM
 - PCPSUICBPARAM
 - CPSUICBPARAM
---

## -description

The CPSUICBPARAM structure is used as the input parameter to [_CPSUICALLBACK](./nc-compstui-_cpsuicallback.md)-typed callback functions.

## -struct-fields

### -field cbSize

CPSUI-supplied size, in bytes, of the CPSUICBPARAM structure.

### -field Reason

CPSUI-supplied value indicating the reason it is calling the callback function. This can be one of the following values:

#### CPSUICB_REASON_ABOUT

The user has clicked on the page's **About** button, and the application previously set the CPSUIF_ABOUT_CALLBACK flag in a [**COMPROPSHEETUI**](./ns-compstui-_compropsheetui.md) structure. CPSUI sets *pCurItem* to the value contained in **pOptItem**, and sets **pOldSel** to point to the **COMPROPSHEETUI** structure.

#### CPSUICB_REASON_APPLYNOW

The user has clicked on the page's **Apply** or **OK** button, and CPSUI has received a [PSN_APPLY](/windows/win32/controls/psm-apply) notification message. CPSUI sets **pCurItem** to point to the option to which **pOptItem** points. It also sets **OldSel** to minus one to indicate that all valid changed option values should be applied now.

#### CPSUICB_REASON_DLGPROC

The option identified by **pCurItem** is a push button ([TVOT_PUSHBUTTON](/windows-hardware/drivers/print/tvot-pushbutton) option type), and the user has clicked on the button.

The push button option's OPTPARAM **Style** field is set to PUSHBUTTON_TYPE_DLGPROC.

#### CPSUICB_REASON_ECB_CHANGED

The option identified by **pCurItem** is an extended check box, and the user has changed the box's state.

#### CPSUICB_REASON_EXTPUSH

The option identified by **pCurItem** is an extended push button, and the user has clicked on the button.

#### CPSUICB_REASON_ITEMS_REVERTED

The user clicked on the page's **Undo** button, and CPSUI has reverted all selections to their original values.

#### CPSUICB_REASON_KILLACTIVE

The property sheet page is about to lose activation, and CPSUI has received a [PSN_KILLACTIVE](/windows/win32/controls/psn-killactive) notification message. CPSUI sets **pCurItem** to the value contained in **pOptItem**, and sets **pOldSel** to point to the [**COMPROPSHEETUI**](./ns-compstui-_compropsheetui.md) structure.

#### CPSUICB_REASON_OPTITEM_SETFOCUS

The option identified by **pCurItem** has received input focus.

#### CPSUICB_REASON_PUSHBUTTON

The option identified by **pCurItem** is a push button ([TVOT_PUSHBUTTON](/windows-hardware/drivers/print/tvot-pushbutton) option type), and the user has clicked on the button.

The push button item's [**OPTPARAM**](./ns-compstui-_optparam.md) **Style**  field is set to PUSHBUTTON_TYPE_CALLBACK.

#### CPSUICB_REASON_SEL_CHANGED

The user has changed the selected value for the option pointed to by **pCurItem**.

#### CPSUICB_REASON_SETACTIVE

The property sheet page is about to become active, and CPSUI has received a [PSN_SETACTIVE](/windows/win32/controls/psn-setactive) notification message. CPSUI sets **pCurItem** to the value contained in **pOptItem**, and sets **pOldSel** to point to the [**COMPROPSHEETUI**](./ns-compstui-_compropsheetui.md) structure.

### -field hDlg

CPSUI-supplied handle to the currently active dialog box.

### -field pOptItem

CPSUI-supplied pointer to an array of [**OPTITEM**](./ns-compstui-_optitem.md) structures. This is the same pointer that the application previously supplied in a [**COMPROPSHEETUI**](./ns-compstui-_compropsheetui.md) structure.

### -field cOptItem

CPSUI-supplied number of OPTITEM structures in the array pointed to by **pOptItem**. This is the same number that the application previously supplied in a [**COMPROPSHEETUI**](./ns-compstui-_compropsheetui.md) structure.

### -field Flags

CPSUI-supplied flags. This is the same set of flags that the application previously supplied in a [**COMPROPSHEETUI**](./ns-compstui-_compropsheetui.md) structure.

### -field pCurItem

CPSUI-supplied pointer to a member of the OPTITEM array pointed to by **pOptItem**. This array member represents the "current" option, which is the one for which the callback function was called.

### -field DUMMYUNIONNAME

Defines the **DUMMYUNIONNAME** union.

### -field DUMMYUNIONNAME.OldSel

If the **Reason** member contains CPSUICB_REASON_SEL_CHANGED, CPSUI sets this union to the previous contents of the **OldSel**/**pOldSel** member of the [**OPTITEM**](./ns-compstui-_optitem.md) structure pointed to by **pCurItem**.

For all other **Reason** values, the contents of this union should be ignored.

### -field DUMMYUNIONNAME.pOldSel

If the **Reason** member contains CPSUICB_REASON_SEL_CHANGED, CPSUI sets this union to the previous contents of the **OldSel**/**pOldSel** member of the [**OPTITEM**](./ns-compstui-_optitem.md) structure pointed to by **pCurItem**.

For all other **Reason** values, the contents of this union should be ignored.

### -field UserData

CPSUI-supplied user data. This is the same value that the application previously supplied in a [**COMPROPSHEETUI**](./ns-compstui-_compropsheetui.md) structure.

### -field Result

Result value supplied by the [_CPSUICALLBACK](./nc-compstui-_cpsuicallback.md)-typed callback function. By default, CPSUI sets this value to CPSUI_OK. After the callback function returns, CPSUI calls its [ComPropSheet](./nc-compstui-pfncompropsheet.md) function with a function code of [CPSFUNC_SET_RESULT](/previous-versions/ff547087(v=vs.85)), supplying the **Reason** member contents as the result value.

This member is used only if the **Reason** member is CPSUICB_REASON_APPLYNOW and the callback function does not return CPSUI_ACTION_NO_APPLY_EXIT.
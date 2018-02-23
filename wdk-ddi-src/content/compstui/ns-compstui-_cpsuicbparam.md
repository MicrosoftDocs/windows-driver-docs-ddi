---
UID: NS:compstui._CPSUICBPARAM
title: "_CPSUICBPARAM"
author: windows-driver-content
description: The CPSUICBPARAM structure is used as the input parameter to _CPSUICALLBACK-typed callback functions.
old-location: print\cpsuicbparam.htm
old-project: print
ms.assetid: b5545efa-6cb4-41d0-9338-be9a269fa193
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PCPSUICBPARAM, compstui/PCPSUICBPARAM, CPSUICBPARAM, cpsuifnc_9e2d49ae-ecb6-4979-aacd-7dd954034e92.xml, PCPSUICBPARAM, print.cpsuicbparam, PCPSUICBPARAM structure pointer [Print Devices], _CPSUICBPARAM, CPSUICBPARAM structure [Print Devices], compstui/CPSUICBPARAM"
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
-	compstui.h
apiname:
-	CPSUICBPARAM
product: Windows
targetos: Windows
req.typenames: CPSUICBPARAM, *PCPSUICBPARAM
---

# _CPSUICBPARAM structure


## -description


The CPSUICBPARAM structure is used as the input parameter to <a href="..\compstui\nc-compstui-_cpsuicallback.md">_CPSUICALLBACK</a>-typed callback functions.


## -syntax


````
typedef struct _CPSUICBPARAM {
  WORD      cbSize;
  WORD      Reason;
  HWND      hDlg;
  POPTITEM  pOptItem;
  WORD      cOptItem;
  WORD      Flags;
  POPTITEM  pCurItem;
  union {
    LONG   OldSel;
    LPTSTR pOldSel;
  };
  ULONG_PTR UserData;
  ULONG_PTR Result;
} CPSUICBPARAM, *PCPSUICBPARAM;
````


## -struct-fields




### -field cbSize

CPSUI-supplied size, in bytes, of the CPSUICBPARAM structure.


### -field Reason

CPSUI-supplied value indicating the reason it is calling the callback function. This can be one of the following values:





#### CPSUICB_REASON_ABOUT

The user has clicked on the page's <b>About</b> button, and the application previously set the CPSUIF_ABOUT_CALLBACK flag in a <a href="..\compstui\ns-compstui-_compropsheetui.md">COMPROPSHEETUI</a> structure. CPSUI sets <i>pCurItem</i> to the value contained in <b>pOptItem</b>, and sets <b>pOldSel</b> to point to the <b>COMPROPSHEETUI</b> structure.





#### CPSUICB_REASON_APPLYNOW

The user has clicked on the page's <b>Apply</b> or <b>OK</b> button, and CPSUI has received a PSN_APPLY notification message (described in the Microsoft Windows SDK documentation). CPSUI sets <b>pCurItem</b> to point to the option to which <b>pOptItem</b> points. It also sets <b>OldSel</b> to minus one to indicate that all valid changed option values should be applied now.





#### CPSUICB_REASON_DLGPROC

The option identified by <b>pCurItem</b> is a push button (<a href="https://msdn.microsoft.com/library/windows/hardware/ff562844">TVOT_PUSHBUTTON</a> option type), and the user has clicked on the button.

The push button option's OPTPARAM <b>Style</b> field is set to PUSHBUTTON_TYPE_DLGPROC.





#### CPSUICB_REASON_ECB_CHANGED

The option identified by <b>pCurItem</b> is an extended check box, and the user has changed the box's state.





#### CPSUICB_REASON_EXTPUSH

The option identified by <b>pCurItem</b> is an extended push button, and the user has clicked on the button.





#### CPSUICB_REASON_ITEMS_REVERTED

The user clicked on the page's <b>Undo</b> button, and CPSUI has reverted all selections to their original values.





#### CPSUICB_REASON_KILLACTIVE

The property sheet page is about to lose activation, and CPSUI has received a PSN_KILLACTIVE notification message (described in the Windows SDK documentation). CPSUI sets <b>pCurItem</b> to the value contained in <b>pOptItem</b>, and sets <b>pOldSel</b> to point to the <a href="..\compstui\ns-compstui-_compropsheetui.md">COMPROPSHEETUI</a> structure.





#### CPSUICB_REASON_OPTITEM_SETFOCUS

The option identified by <b>pCurItem</b> has received input focus.





#### CPSUICB_REASON_PUSHBUTTON

The option identified by <b>pCurItem</b> is a push button (<a href="https://msdn.microsoft.com/library/windows/hardware/ff562844">TVOT_PUSHBUTTON</a> option type), and the user has clicked on the button.

The push button item's <a href="..\compstui\ns-compstui-_optparam.md">OPTPARAM</a> <b>Style</b>  field is set to PUSHBUTTON_TYPE_CALLBACK.





#### CPSUICB_REASON_SEL_CHANGED

The user has changed the selected value for the option pointed to by <b>pCurItem</b>.





#### CPSUICB_REASON_SETACTIVE

The property sheet page is about to become active, and CPSUI has received a PSN_SETACTIVE notification message (described in the Windows SDK documentation). CPSUI sets <b>pCurItem</b> to the value contained in <b>pOptItem</b>, and sets <b>pOldSel</b> to point to the <a href="..\compstui\ns-compstui-_compropsheetui.md">COMPROPSHEETUI</a> structure.


### -field hDlg

CPSUI-supplied handle to the currently active dialog box.


### -field pOptItem

CPSUI-supplied pointer to an array of <a href="..\compstui\ns-compstui-_optitem.md">OPTITEM</a> structures. This is the same pointer that the application previously supplied in a <a href="..\compstui\ns-compstui-_compropsheetui.md">COMPROPSHEETUI</a> structure.


### -field cOptItem

CPSUI-supplied number of OPTITEM structures in the array pointed to by <b>pOptItem</b>. This is the same number that the application previously supplied in a <a href="..\compstui\ns-compstui-_compropsheetui.md">COMPROPSHEETUI</a> structure.


### -field Flags

CPSUI-supplied flags. This is the same set of flags that the application previously supplied in a <a href="..\compstui\ns-compstui-_compropsheetui.md">COMPROPSHEETUI</a> structure.


### -field pCurItem

CPSUI-supplied pointer to a member of the OPTITEM array pointed to by <b>pOptItem</b>. This array member represents the "current" option, which is the one for which the callback function was called.


### -field DUMMYUNIONNAME

 


### -field UserData

CPSUI-supplied user data. This is the same value that the application previously supplied in a <a href="..\compstui\ns-compstui-_compropsheetui.md">COMPROPSHEETUI</a> structure.


### -field Result

Result value supplied by the <a href="..\compstui\nc-compstui-_cpsuicallback.md">_CPSUICALLBACK</a>-typed callback function. By default, CPSUI sets this value to CPSUI_OK. After the callback function returns, CPSUI calls its <a href="..\compstui\nc-compstui-pfncompropsheet.md">ComPropSheet</a> function with a function code of <a href="https://msdn.microsoft.com/library/windows/hardware/ff547087">CPSFUNC_SET_RESULT</a>, supplying the <b>Reason</b> member contents as the result value.

This member is used only if the <b>Reason</b> member is CPSUICB_REASON_APPLYNOW and the callback function does not return CPSUI_ACTION_NO_APPLY_EXIT.


#### - OldSel

If the <b>Reason</b> member contains CPSUICB_REASON_SEL_CHANGED, CPSUI sets this union to the previous contents of the <b>OldSel</b>/<b>pOldSel</b> member of the <a href="..\compstui\ns-compstui-_optitem.md">OPTITEM</a> structure pointed to by <b>pCurItem</b>.

For all other <b>Reason</b> values, the contents of this union should be ignored.


#### - pOldSel

If the <b>Reason</b> member contains CPSUICB_REASON_SEL_CHANGED, CPSUI sets this union to the previous contents of the <b>OldSel</b>/<b>pOldSel</b> member of the <a href="..\compstui\ns-compstui-_optitem.md">OPTITEM</a> structure pointed to by <b>pCurItem</b>.

For all other <b>Reason</b> values, the contents of this union should be ignored.


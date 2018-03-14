---
UID: NA:compstui
ms.assetid: b7caed49-be56-3b9d-90b7-dce65c62402e
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Compstui.h header



This header is used by print. For more information, see
- [print](../_print/index.md)

Compstui.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [CommonPropertySheetUIA function](nf-compstui-commonpropertysheetuia.md) | CPSUI's CommonPropertySheetUI function displays property sheet pages and allows user modifications to displayed values. |
| [CommonPropertySheetUIW function](nf-compstui-commonpropertysheetuiw.md) | CPSUI's CommonPropertySheetUI function displays property sheet pages and allows user modifications to displayed values. |
| [GetCPSUIUserData function](nf-compstui-getcpsuiuserdata.md) | CPSUI's GetCPSUIUserData function retrieves data that was previously stored using the SetCPSUIUserData function. |
| [SetCPSUIUserData function](nf-compstui-setcpsuiuserdata.md) | CPSUI's SetCPSUIUserData function allows CPSUI applications (including printer interface DLLs) to associate nondisplayed data with a property sheet dialog box. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PFNCOMPROPSHEET callback](nc-compstui-pfncompropsheet.md) | Pointer to the common UI callback function to add, delete, or set user data. |
| [PFNPROPSHEETUI callback](nc-compstui-pfnpropsheetui.md) | The PFNPROPSHEETUI function type is used by CPSUI applications (including printer interface DLLs) for defining page creation callbacks, which specify property sheet pages for creation. |
| [_CPSUICALLBACK callback](nc-compstui-_cpsuicallback.md) | The _CPSUICALLBACK function type is used by CPSUI applications (including printer interface DLLs) for defining a callback function intended for use as a CPSUI message handler. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_COMPROPSHEETUI structure](ns-compstui-_compropsheetui.md) | The COMPROPSHEETUI structure is used as an input parameter to CPSUI's ComPropSheet function, if the function code is CPSFUNC_ADD_PCOMPROPSHEETUI. All structure members must be supplied by the caller of ComPropSheet. |
| [_CPSUICBPARAM structure](ns-compstui-_cpsuicbparam.md) | The CPSUICBPARAM structure is used as the input parameter to _CPSUICALLBACK-typed callback functions. |
| [_CPSUIDATABLOCK structure](ns-compstui-_cpsuidatablock.md) | The CPSUIDATABLOCK structure is used as a parameter for the ComPropSheet function, if the function code is CPSFUNC_SET_DATABLOCK or CPSFUNC_QUERY_DATABLOCK. |
| [_DLGPAGE structure](ns-compstui-_dlgpage.md) | The DLGPAGE structure is used for specifying a property sheet page to CPSUI's ComPropSheet function. The structure's address is included in a COMPROPSHEETUI structure, and all member values are supplied by the ComPropSheet caller. |
| [_EXTCHKBOX structure](ns-compstui-_extchkbox.md) | The EXTCHKBOX structure is used by CPSUI applications (including printer interface DLLs) for specifying an extended check box, which can be added to a property sheet page option. |
| [_EXTPUSH structure](ns-compstui-_extpush.md) | The EXTPUSH structure is used by CPSUI applications (including printer interface DLLs) for specifying an extended push button, which can be added to a property sheet page option. When the button is pushed, a new dialog can be displayed. |
| [_INSERTPSUIPAGE_INFO structure](ns-compstui-_insertpsuipage_info.md) | The INSERTPSUIPAGE_INFO structure is used as an input parameter to CPSUI's ComPropSheet function, if the function code is CPSFUNC_INSERT_PSUIPAGE. All member values must be supplied by the ComPropSheet caller. |
| [_OIEXT structure](ns-compstui-_oiext.md) | The OIEXT structure supplies additional, optional information about a property sheet page option that is described by an OPTITEM structure. |
| [_OPTCOMBO structure](ns-compstui-_optcombo.md) | "." |
| [_OPTITEM structure](ns-compstui-_optitem.md) | The OPTITEM structure is used by CPSUI applications (including printer interface DLLs) for describing one property sheet option on a property sheet page, if the page is described by a COMPROPSHEETUI structure. |
| [_OPTPARAM structure](ns-compstui-_optparam.md) | An array of OPTPARAM structures is used by CPSUI applications (including printer interface DLLs) for describing all the parameter values associated with a property sheet option. The array's address is included in an OPTTYPE structure. |
| [_OPTTYPE structure](ns-compstui-_opttype.md) | The OPTTYPE structure is used by CPSUI applications (including printer interface DLLs) for describing the type and other characteristics of a property sheet option, if the option is specified by an OPTITEM structure. |
| [_PROPSHEETUI_GETICON_INFO structure](ns-compstui-_propsheetui_geticon_info.md) | The PROPSHEETUI_GETICON_INFO structure is used as an input parameter to an application's PFNPROPSHEETUI-typed function, when the function is called with a reason value of PROPSHEETUI_REASON_GET_ICON. |
| [_PROPSHEETUI_INFO structure](ns-compstui-_propsheetui_info.md) | The PROPSHEETUI_INFO structure is used as an input parameter to PFNPROPSHEETUI-typed functions. |
| [_PROPSHEETUI_INFO_HEADER structure](ns-compstui-_propsheetui_info_header.md) | The PROPSHEETUI_INFO_HEADER structure is used as an input parameter to an application's PFNPROPSHEETUI-typed function, when the function is called with a reason value of PROPSHEETUI_REASON_GET_INFO_HEADER. |
| [_PSPINFO structure](ns-compstui-_pspinfo.md) | The PSPINFO structure is used as an input parameter to a property sheet page's dialog box procedure, when the Windows message is WM_INITDIALOG. The dialog box procedure's address is specified in a DLGPAGE structure. |
| [_SETRESULT_INFO structure](ns-compstui-_setresult_info.md) | The SETRESULT_INFO structure is used as an input parameter to an application's PFNPROPSHEETUI-typed callback function. |

---
UID: NS:compstui._OPTITEM
title: _OPTITEM (compstui.h)
description: The OPTITEM structure is used by CPSUI applications (including printer interface DLLs) for describing one property sheet option on a property sheet page, if the page is described by a COMPROPSHEETUI structure.
old-location: print\optitem.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["OPTITEM structure"]
ms.keywords: "*POPTITEM, OPTITEM, OPTITEM structure [Print Devices], POPTITEM, POPTITEM structure pointer [Print Devices], _OPTITEM, compstui/OPTITEM, compstui/POPTITEM, cpsuifnc_0d0609c0-cb09-4428-b083-8db736570309.xml, print.optitem"
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
req.typenames: OPTITEM, *POPTITEM
f1_keywords:
 - _OPTITEM
 - compstui/_OPTITEM
 - POPTITEM
 - compstui/POPTITEM
 - OPTITEM
 - compstui/OPTITEM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - compstui.h
api_name:
 - OPTITEM
---

# _OPTITEM structure


## -description

The OPTITEM structure is used by CPSUI applications (including printer interface DLLs) for describing one [property sheet option](/windows-hardware/drivers/print/property-sheet-options) on a property sheet page, if the page is described by a [COMPROPSHEETUI](./ns-compstui-_compropsheetui.md) structure.

## -struct-fields

### -field cbSize

Size, in bytes, of the OPTITEM structure.

### -field Level

Specifies the level of this option in the treeview. For more information, see the following Remarks section.

### -field DlgPageIdx

Identifies the dialog to which the option belongs. Specifies an array index into the DLGPAGE array pointed to by the **pDlgPage** member of the [COMPROPSHEETUI](./ns-compstui-_compropsheetui.md) structure.

If **pDlgPage** points to a CPSUI-supplied, predefined DLGPAGE structure, CPSUI supplies this index.

### -field Flags

Optional bit flags that modify the option's characteristics. The OPTIF_CHANGEONCE flag is set by CPSUI; all other flags are set by the caller. Any combination of the following flags can be set.

#### OPTIF_CALLBACK

When a user modifies the option, CPSUI should call the [_CPSUICALLBACK](./nc-compstui-_cpsuicallback.md)-typed callback function specified in the [COMPROPSHEETUI](./ns-compstui-_compropsheetui.md) structure.

#### OPTIF_CHANGED

The **_CPSUICALLBACK**-typed callback function should set this flag if it modified the option, so that CPSUI will redisplay it.

#### OPTIF_CHANGEONCE

CPSUI sets this bit if a user modified the option.

#### OPTIF_COLLAPSE

Collapse this option and its children so that it is not expanded in the treeview.

#### OPTIF_DISABLED

Disables the option so that it is not user-modifiable.

#### OPTIF_ECB_CHECKED

The associated extended check box is in the checked state.

#### OPTIF_EXT_IS_EXTPUSH

If set, the **pExtPush** member is valid (unless **NULL**).

If not set, the **pExtChkBox** member is valid (unless **NULL**).

#### OPTIF_EXT_DISABLED

The extended check box or extended push button is not selectable.

#### OPTIF_EXT_HIDE

CPSUI will not display the extended check box or extended push button.

#### OPTIF_HAS_POIEXT

If set, the **pOIExt** member is valid.

#### OPTIF_HIDE

CPSUI will not display this option in the treeview. CPSUI examines this flag only when initially creating the treeview, so changing the flag from its initial value has no effect.

#### OPTIF_INITIAL_TVITEM

If set, CPSUI sets the initial window focus to this option when it displays the treeview. CPSUI expands tree nodes and scrolls the option into view as necessary. If the option is hidden, or if this flag is not set for any OPTITEM structure, CPSUI chooses the initial focus.

#### OPTIF_NO_GROUPBOX_NAME

If not set, and **pOptype** is not zero, CPSUI uses the **pName** string as the groupbox title.

If set, CPSUI provides a groupbox title.

#### OPTIF_OVERLAY_NO_ICON

If set CPSUI overlays its IDI_CPSUI_NO icon onto the icon associated with the option. (See the **Sel/pSel** member.)

#### OPTIF_OVERLAY_STOP_ICON

If set, CPSUI overlays its IDI_CPSUI_STOP icon onto the icon associated with the option. (See the **Sel/pSel** member.)

#### OPTIF_OVERLAY_WARNING_ICON

If set, CPSUI overlays its IDI_CPSUI_WARNING icon onto the icon associated with the option. (See the **Sel/pSel** member.)

#### OPTIF_SEL_AS_HICON

If set, the **Sel** member contains an icon handle.

If not set, the **Sel** member contains an icon resource identifier.

This flag can only be used when **pOptType** contains **NULL**.

### -field UserData

Optional 32-bit value that can be set and used by the caller.

(Printer interface DLLs for [Unidrv](/windows-hardware/drivers/print/microsoft-universal-printer-driver) and [Pscript](/windows-hardware/drivers/print/microsoft-postscript-printer-driver) use this member to supply a pointer to a [USERDATA](../printoem/ns-printoem-_userdata.md) structure. [User interface plug-ins](/windows-hardware/drivers/print/user-interface-plug-ins) can reference this structure.)

### -field pName

String identifier representing a localized, displayable option name. This can be a 32-bit pointer to a NULL-terminated string, or it can be a 16-bit string resource identifier, with HIWORD set to zero. (Also see the description of **DMPubID**, below.)

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.Sel

This union indicates the option's currently selected parameter value. Its usage is dependent on the [CPSUI option type](/windows-hardware/drivers/print/cpsui-option-types).

If **pOptType** is **NULL**, the option has no parameters, so this union identifies an icon to be associated with the treeview node for the option. The icon identifier can be either an icon handle or an icon resource identifier, as indicated by OPTIF_SEL_AS_HICON in **Flags**.

### -field DUMMYUNIONNAME.pSel

This union indicates the option's currently selected parameter value. Its usage is dependent on the [CPSUI option type](/windows-hardware/drivers/print/cpsui-option-types).

If **pOptType** is **NULL**, the option has no parameters, so this union identifies an icon to be associated with the treeview node for the option. The icon identifier can be either an icon handle or an icon resource identifier, as indicated by OPTIF_SEL_AS_HICON in **Flags**.

### -field DUMMYUNIONNAME2

### -field DUMMYUNIONNAME2.pExtChkBox

Pointer to EXTCHKBOX structure

### -field DUMMYUNIONNAME2.pExtPush

This union can be a pointer to an [EXTCHKBOX](./ns-compstui-_extchkbox.md) structure, a pointer to an [EXTPUSH](./ns-compstui-_extpush.md) structure, or **NULL**.

An OPTITEM structure can optionally have an EXTCHKBOX structure, an EXTPUSH structure, or neither, associated with it. If this union is not **NULL**, and if OPTIF_EXT_IS_EXTPUSH is set in **Flags**, **pExtPush** is valid. If the flag is not set, **pExtChkBox** is valid.

### -field pOptType

Pointer to an [OPTTYPE](./ns-compstui-_opttype.md) structure that describes the option's display type. If **NULL**, the option has no parameters and is used as a parent to options with a higher **Level** value. The child options must immediately follow the parent in the OPTITEM array. (See the following Remarks section.)

### -field HelpIndex

Help file index, which identifies help text to be associated with the option. If zero, help file text does not exist for this option. Note that the **pOIExt** member of this structure must be set with the address of an [OIEXT](./ns-compstui-_oiext.md) structure in order for help text functionality to exist.

### -field DMPubID

This member is meant for use by printer interface DLLs, when creating a **Document Properties** property sheet (see [DrvDocumentPropertySheets](../winddiui/nf-winddiui-drvdocumentpropertysheets.md)). It is a constant value specifying which, if any, public member of the [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure is associated with this option. The following table lists available constants, the associated DEVMODE structure member, and the required value for **pName** for each constant.

| Constant Value | Required pName Value | Structure Member |
| --- | --- | --- |
| DMPUB_COLOR | **dmColor** | IDS_CPSUI_COLOR_APPERANCE |
| DMPUB_COPIES_COLLATE | **dmCopies** and **dmCollate** | IDS_CPSUI_COPIES |
| DMPUB_DEFSOURCE | **dmDefSource** | IDS_CPSUI_SOURCE |
| DMPUB_DITHERTYPE | **dmDitherType** | IDS_CPSUI_DITHERING |
| DMPUB_DUPLEX | **dmDuplex** | IDS_CPSUI_DUPLEX |
| DMPUB_FORMNAME | **dmFormName** | IDS_CPSUI_FORMNAME |
| DMPUB_ICMINTENT | **dmICMIntent** | IDS_CPSUI_ICMINTENT |
| DMPUB_ICMMETHOD | **dmICMMethod** | IDS_CPSUI_ICMMETHOD |
| DMPUB_MEDIATYPE | **dmMediaType** | IDS_CPSUI_MEDIA |
| DMPUB_NUP | Not contained in public section of DEVMODE. | IDS_CPSUI_NUP |
| DMPUB_ORIENTATION | **dmOrientation** | IDS_CPSUI_ORIENTATION |
| DMPUB_OUTPUTBIN | Not contained in public section of DEVMODE. | IDS_CPSUI_OUTPUTBIN |
| DMPUB_PAGEORDER | Not contained in public section of DEVMODE. | IDS_CPSUI_PAGEORDER |
| DMPUB_PRINTQUALITY | **dmPrintQuality** | IDS_CPSUI_PRINTQUALITY or IDS_CPSUI_RESOLUTION. If not specified, the default name is IDS_CPSUI_RESOLUTION. |
| DMPUB_QUALITY | Not contained in public section of DEVMODE. | IDS_CPSUI_QUALITY_SETTINGS |
| DMPUB_SCALE | **dmScale** | IDS_CPSUI_SCALE |
| DMPUB_TTOPTION | **dmTTOption** | IDS_CPSUI_TTOPTION |
| DMPUB_NONE | Not contained in public section of DEVMODE. | &nbsp; |
| Greater than or equal to DMPUB_USER | Ignored by CPSUI, can be a caller-defined value. | &nbsp; |

CPSUI does not maintain a DEVMODE structure. The application is responsible for copying user-selected option parameters into a DEVMODE structure. CPSUI uses **DMPubID** contents to determine treeview placement of standard options, and to determine the contents of the **Layout** and **Paper/Quality** tabs (see the **pDlgPage** member of the [COMPROPSHEETUI](./ns-compstui-_compropsheetui.md) structure).

For additional information about using the **DMPubID** member, see the following Remarks section.

### -field UserItemID

Optional application-supplied value that can be used for option identification purposes. Not referenced by CPSUI.

### -field wReserved

Reserved, must be initialized to zero.

### -field pOIExt

Pointer to an optional [OIEXT](./ns-compstui-_oiext.md) structure. The caller is responsible for allocating storage for this structure.

### -field dwReserved

Reserved, must be initialized to zero.

## -remarks

OPTITEM structures should be placed in an array, and the array's address should be placed in the **pOptItem** member of a [COMPROPSHEETUI](./ns-compstui-_compropsheetui.md) structure.

The **Level** member allows you to create child nodes in the treeview. For example, to create a set of option nodes under a level 1 parent node, specify level 2 for each child node and include their OPTITEM structures in the OPTITEM array, immediately after the parent's OPTITEM structure. In the parent's OPTITEM structure, **pOptType** should be **NULL**.

The treeview root node is level 0. Options displayed when a user expands the root node are level 1. The maximum number of levels is 256.

For option values that are stored in a printer's DEVMODE structure, the **DMPubID** member must identify the option. For each **DMPubID** value that is used, a printer interface DLL must specify the [CPSUI option type](/windows-hardware/drivers/print/cpsui-option-types) listed in the following table.

| DMPubID Value | Required CPSUI Option Type |
| --- | --- | --- |
| DMPUB_COLOR | [TVOT_2STATES](/windows-hardware/drivers/print/tvot-2states) |
| DMPUB_COPIES_COLLATE | [TVOT_UDARROW](/windows-hardware/drivers/print/tvot-udarrow) plus [EXTCHKBOX](./ns-compstui-_extchkbox.md) (See comments following this table.) |
| DMPUB_DEFSOURCE | [TVOT_LISTBOX](/windows-hardware/drivers/print/tvot-listbox) |
| DMPUB_DITHERTYPE | [TVOT_LISTBOX](/windows-hardware/drivers/print/tvot-listbox) |
| DMPUB_DUPLEX | [TVOT_2STATES](/windows-hardware/drivers/print/tvot-2states) or [TVOT_3STATES](/windows-hardware/drivers/print/tvot-3states) |
| DMPUB_FORMNAME | [TVOT_LISTBOX](/windows-hardware/drivers/print/tvot-listbox) |
| DMPUB_ICMINTENT | [TVOT_2STATES](/windows-hardware/drivers/print/tvot-2states) or [TVOT_3STATES](/windows-hardware/drivers/print/tvot-3states) |
| DMPUB_ICMMETHOD | [TVOT_2STATES](/windows-hardware/drivers/print/tvot-2states) or [TVOT_3STATES](/windows-hardware/drivers/print/tvot-3states) |
| DMPUB_MEDIATYPE | [TVOT_LISTBOX](/windows-hardware/drivers/print/tvot-listbox) |
| DMPUB_NUP | [TVOT_LISTBOX](/windows-hardware/drivers/print/tvot-listbox) |
| DMPUB_ORIENTATION | [TVOT_2STATES](/windows-hardware/drivers/print/tvot-2states) or [TVOT_3STATES](/windows-hardware/drivers/print/tvot-3states) |
| DMPUB_OUTPUTBIN | [TVOT_LISTBOX](/windows-hardware/drivers/print/tvot-listbox) |
| DMPUB_PAGEORDER | [TVOT_2STATES](/windows-hardware/drivers/print/tvot-2states) or [TVOT_3STATES](/windows-hardware/drivers/print/tvot-3states) |
| DMPUB_PRINTQUALITY | [TVOT_LISTBOX](/windows-hardware/drivers/print/tvot-listbox) |
| DMPUB_QUALITY | [TVOT_2STATES](/windows-hardware/drivers/print/tvot-2states) or [TVOT_3STATES](/windows-hardware/drivers/print/tvot-3states) |
| DMPUB_SCALE | [TVOT_UDARROW](/windows-hardware/drivers/print/tvot-udarrow) |
| DMPUB_TTOPTION | [TVOT_LISTBOX](/windows-hardware/drivers/print/tvot-listbox) |

If **DMPubID** is DMPUB_COPIES_COLLATE and the printer can collate copies, an extended check box (EXTCHKBOX structure) must be provided. The EXTCHCKBOX structure's members must be set as follows:

```cpp
pExtCheckbox->cbSize = sizeof(EXTCHKBOX);
pExtCheckbox->pTitle = (PWSTR) IDS_CPSUI_COLLATE;
pExtCheckbox->pCheckedName = (PWSTR) IDS_CPSUI_COLLATED;
pExtCheckbox->IconID = IDI_CPSUI_COLLATE;
pExtCheckbox->Flags = ECBF_CHECKNAME_ONLY_ENABLED;
pExtCheckbox->pSeparator = (PWSTR)IDS_CPSUI_SLASH_SEP;
```

If OPTIF_EXT_HIDE is not set in **Flags**, CPSUI enables the check box if a user requests more than one copy, and disables it if only one copy is requested.

Additionally, CPSUI sets the option's display text to **copy** for one copy and **copies** for more than one copy.

If **DMPubID** is DMPUB_COLOR, its first [OPTPARAM](./ns-compstui-_optparam.md) structure (**Sel**=0) must represent Gray Scale, and **pData** in the OPTPARAM structure must be IDS_CPSUI_GRAYSCALE. Its second OPTPARAM structure (**Sel**=1) must represent Color, and **pData** in the OPTPARAM structure must be IDS_CPSUI_COLOR. If another option's **DMPubID** is DMPUB_ICMINTENT and if Color is not selected, CPSUI disables the option for which DMPUB_ICMINTENT is specified.

CPSUI disables color matching when Color is not selected.

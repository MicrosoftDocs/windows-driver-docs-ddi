---
UID: NS:dbgeng._DEBUG_REGISTER_DESCRIPTION
title: "_DEBUG_REGISTER_DESCRIPTION"
author: windows-driver-content
description: The DEBUG_REGISTER_DESCRIPTION structure is returned by GetDescription to describe a processor's register.
old-location: debugger\debug_register_description.htm
old-project: debugger
ms.assetid: 92e7800d-4de6-498c-87f8-8690d7e8fc51
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PDEBUG_REGISTER_DESCRIPTION, DEBUG_REGISTER_DESCRIPTION, DEBUG_REGISTER_DESCRIPTION structure [Windows Debugging], PDEBUG_REGISTER_DESCRIPTION, PDEBUG_REGISTER_DESCRIPTION structure pointer [Windows Debugging], Structures_a7dd005e-3383-4c58-8b01-fe2127d6bc20.xml, _DEBUG_REGISTER_DESCRIPTION, dbgeng/DEBUG_REGISTER_DESCRIPTION, dbgeng/PDEBUG_REGISTER_DESCRIPTION, debugger.debug_register_description"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
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
-	DbgEng.h
apiname:
-	DEBUG_REGISTER_DESCRIPTION
product: Windows
targetos: Windows
req.typenames: DEBUG_REGISTER_DESCRIPTION, *PDEBUG_REGISTER_DESCRIPTION
---

# _DEBUG_REGISTER_DESCRIPTION structure


## -description


The <b>DEBUG_REGISTER_DESCRIPTION</b> structure is returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff546575">GetDescription</a> to describe a processor's register.


## -syntax


````
typedef struct _DEBUG_REGISTER_DESCRIPTION {
  ULONG   Type;
  ULONG   Flags;
  ULONG   SubregMaster;
  ULONG   SubregLength;
  ULONG64 SubregMask;
  ULONG   SubregShift;
  ULONG   Reserved0;
} DEBUG_REGISTER_DESCRIPTION, *PDEBUG_REGISTER_DESCRIPTION;
````


## -struct-fields




### -field Type

The type of value that this register holds.  The possible values are the same as for the <b>Type</b> field in the <a href="..\dbgeng\ns-dbgeng-_debug_value.md">DEBUG_VALUE</a> structure.


### -field Flags

A bit field of flags for the register.  Currently, the only bit that can be set is DEBUG_REGISTER_SUB_REGISTER, which indicates that this register is a subregister.


### -field SubregMaster

The index of the register of which this register is a sub-register.  This field is only used if the DEBUG_REGISTER_SUB_REGISTER bit is set in <b>Flags</b>; otherwise, it is set to zero.


### -field SubregLength

The size, in bits, of this sub-register.  This field is only used if the DEBUG_REGISTER_SUB_REGISTER bit is set in <b>Flags</b>; otherwise, it is set to zero.


### -field SubregMask

The bit mask that converts the register specified in <b>SubregMaster</b> into this sub-register.  This field is only used if the DEBUG_REGISTER_SUB_REGISTER bit is set in <b>Flags</b>; otherwise, it is set to zero.


### -field SubregShift

The bit shift that converts the register specified in <b>SubregMaster</b> into this sub-register.  This field is only used if the DEBUG_REGISTER_SUB_REGISTER bit is set in <b>Flags</b>; otherwise, it is set to zero.


### -field Reserved0

Reserved for system use.


## -remarks



If this register is a subregister, the value of the full register can be turned into the value of the sub-register by first shifting <b>SubregShift</b> bits to the right and then combining the result with <b>SubregMask</b> using the bitwise-AND operator.  The size of the sub-register (<b>SubregLength</b>) is the number of bits set in <b>SubregMask</b>.

For general information about registers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.




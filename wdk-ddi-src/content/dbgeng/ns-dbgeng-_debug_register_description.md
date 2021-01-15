---
UID: NS:dbgeng._DEBUG_REGISTER_DESCRIPTION
title: _DEBUG_REGISTER_DESCRIPTION (dbgeng.h)
description: The DEBUG_REGISTER_DESCRIPTION structure is returned by GetDescription to describe a processor's register.
old-location: debugger\debug_register_description.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["DEBUG_REGISTER_DESCRIPTION structure"]
ms.keywords: "*PDEBUG_REGISTER_DESCRIPTION, DEBUG_REGISTER_DESCRIPTION, DEBUG_REGISTER_DESCRIPTION structure [Windows Debugging], PDEBUG_REGISTER_DESCRIPTION, PDEBUG_REGISTER_DESCRIPTION structure pointer [Windows Debugging], Structures_a7dd005e-3383-4c58-8b01-fe2127d6bc20.xml, _DEBUG_REGISTER_DESCRIPTION, dbgeng/DEBUG_REGISTER_DESCRIPTION, dbgeng/PDEBUG_REGISTER_DESCRIPTION, debugger.debug_register_description"
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
targetos: Windows
req.typenames: DEBUG_REGISTER_DESCRIPTION, *PDEBUG_REGISTER_DESCRIPTION
f1_keywords:
 - _DEBUG_REGISTER_DESCRIPTION
 - dbgeng/_DEBUG_REGISTER_DESCRIPTION
 - PDEBUG_REGISTER_DESCRIPTION
 - dbgeng/PDEBUG_REGISTER_DESCRIPTION
 - DEBUG_REGISTER_DESCRIPTION
 - dbgeng/DEBUG_REGISTER_DESCRIPTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - DbgEng.h
api_name:
 - _DEBUG_REGISTER_DESCRIPTION
 - PDEBUG_REGISTER_DESCRIPTION
 - DEBUG_REGISTER_DESCRIPTION
---

# _DEBUG_REGISTER_DESCRIPTION structure


## -description

The <b>DEBUG_REGISTER_DESCRIPTION</b> structure is returned by <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getdescription">GetDescription</a> to describe a processor's register.

## -struct-fields

### -field Type

The type of value that this register holds.  The possible values are the same as for the <b>Type</b> field in the <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_value">DEBUG_VALUE</a> structure.

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

For general information about registers, see <a href="/windows-hardware/drivers/debugger/registers">Registers</a>.


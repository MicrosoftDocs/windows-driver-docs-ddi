---
description: "Learn more about: Debugger APIs"
UID: TP:debugger
title: Debugger overview
ms.assetid: 025d7cc4-309d-33e6-8813-f58445c3acaf
ms.date: 07/27/2023
keywords: ["Debugger APIs"]
ms.keywords: 
ms.topic: reference
tech.root: debugger
---

# Debugger APIs

## -description

To develop Debugger apps, you can work with these headers:

 * [dbgeng.h](../dbgeng/index.md)
 * [dbgmodel.h](../dbgmodel/index.md)
 * [engextcpp.hpp](../engextcpp/index.md)
 * [extsfns.h](../extsfns/index.md)
 * [wdbgexts.h](../wdbgexts/index.md)

For the programming guide information, see [Debugging Resources](/windows-hardware/drivers/debugger/debugging-resources).

Use the following header to add 2PF debugger transport support to miniport NDIS drivers, to allow increased performance for high speed network adapters. This feature is available in Windows 11 and later.

 * [kdnetpf.h](../kdnetpf/index.md)

## Macros

| Title   | Description   |
| ---- |:---- |
| [EXT_COMMAND macro](../engextcpp/nf-engextcpp-ext_command.md) | The EXT_COMMAND macro is used to define an extension command that was declared by using the EXT_COMMAND_METHOD macro.An extension command is defined as follows |
| [EXT_COMMAND_METHOD macro](../engextcpp/nf-engextcpp-ext_command_method.md) | The EXT_COMMAND_METHOD macro declares an extension command from inside the definition of the EXT_CLASS class. |
| [GetDebuggerData macro](../wdbgexts/nf-wdbgexts-getdebuggerdata.md) | The GetDebuggerData function retrieves information stored in a data block. |
| [GetFieldValue macro](../wdbgexts/nf-wdbgexts-getfieldvalue.md) | The GetFieldValue macro is a thin wrapper around the GetFieldData function. It is provided as a convenience for reading the value of a member in a structure. |
| [GetKdContext macro](../wdbgexts/nf-wdbgexts-getkdcontext.md) | The GetKdContext function returns the total number of processors and the number of the current processor in the structure ppi points to. |


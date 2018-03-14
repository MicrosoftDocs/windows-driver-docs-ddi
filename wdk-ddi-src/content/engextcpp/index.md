---
UID: NA:engextcpp
ms.assetid: 4849a6b1-830f-3826-8f7f-f7451944fa5f
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Engextcpp.h header



This header is used by Debugger. For more information, see
- [Debugger](../_debugger/index.md)

Engextcpp.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [ExtKnownStruct structure](ns-engextcpp-extknownstruct.md) | The ExtKnownStruct structure is used to specify how a target's structure can be formatted for output. |

## Classes

| Title   | Description   |
| ---- |:---- |
| [ExtExtension class](nl-engextcpp-extextension~r1.md) | The ExtExtension class is the base class for the C++ class that represents the EngExtCpp extension library. |
| [ExtRemoteData class](nl-engextcpp-extremotedata.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteList class](nl-engextcpp-extremotelist.md) | The ExtRemoteList class provides a wrapper around a singly-linked or doubly-linked list. The class contains methods that can be used to move both forward and backward through the list. |
| [ExtRemoteTyped class](nl-engextcpp-extremotetyped.md) | The ExtRemoteTyped class provides the ability to manipulate typed data on the target. |
| [ExtRemoteTypedList class](nl-engextcpp-extremotetypedlist.md) | The ExtRemoteTypedList class extends the ExtRemoteList class. The ExtRemoteTypedList class adds type information allowing each item in the list to be represented by an instance of the ExtRemoteTyped class. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [EXT_COMMAND macro](nf-engextcpp-ext_command.md) | The EXT_COMMAND macro is used to define an extension command that was declared by using the EXT_COMMAND_METHOD macro.An extension command is defined as follows |
| [EXT_COMMAND_METHOD macro](nf-engextcpp-ext_command_method.md) | The EXT_COMMAND_METHOD macro declares an extension command from inside the definition of the EXT_CLASS class. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [ExtBuffer::Copy method](nf-engextcpp-extbuffer-copy.md) | The Copy method sets the typed data represented by the ExtRemoteTyped object by copying the information from another object. |
| [ExtBuffer::Set method](nf-engextcpp-extbuffer-set.md) | The Set method sets the typed data represented by the ExtRemoteTyped object. |
| [ExtBuffer::operator= method](nf-engextcpp-extbuffer-operator=.md) | The operator= overloaded assignment operator sets the typed data represented by the ExtRemoteTyped object by copying the information from another object. |
| [ExtCheckedPointer::Set method](nf-engextcpp-extcheckedpointer-set.md) | The Set method sets the typed data represented by the ExtRemoteTyped object. |
| [ExtCheckedPointer::operator= method](nf-engextcpp-extcheckedpointer-operator=.md) | The operator= overloaded assignment operator sets the typed data represented by the ExtRemoteTyped object by copying the information from another object. |
| [ExtDeclAlignedBuffer::operator= method](nf-engextcpp-extdeclalignedbuffer-operator=.md) | The operator= overloaded assignment operator sets the typed data represented by the ExtRemoteTyped object by copying the information from another object. |
| [ExtDeclBuffer::operator= method](nf-engextcpp-extdeclbuffer-operator=.md) | The operator= overloaded assignment operator sets the typed data represented by the ExtRemoteTyped object by copying the information from another object. |
| [ExtDeleteHolder::Set method](nf-engextcpp-extdeleteholder-set.md) | The Set method sets the typed data represented by the ExtRemoteTyped object. |
| [ExtDeleteHolder::operator= method](nf-engextcpp-extdeleteholder-operator=.md) | The operator= overloaded assignment operator sets the typed data represented by the ExtRemoteTyped object by copying the information from another object. |
| [ExtExtension::GetArgStr method](nf-engextcpp-extextension-getargstr.md) | The GetArgStr method returns a named string argument from the command line used to invoke the current extension command. |
| [ExtExtension::GetArgU64 method](nf-engextcpp-extextension-getargu64.md) | The GetArgU64 method returns the value of a named expression argument from the command line used to invoke the current extension command. |
| [ExtExtension::GetNumUnnamedArgs method](nf-engextcpp-extextension-getnumunnamedargs.md) | The GetNumUnnamedArgs method returns the number of unnamed arguments in the command line used to invoke the current extension command. |
| [ExtExtension::GetRawArgStr method](nf-engextcpp-extextension-getrawargstr.md) | The GetRawArgStr method returns a string that represents the arguments passed to the extension command. |
| [ExtExtension::GetUnnamedArgStr method](nf-engextcpp-extextension-getunnamedargstr.md) | The GetUnnamedArgStr method returns an unnamed string argument from the command line used to invoke the current extension command. |
| [ExtExtension::GetUnnamedArgU64 method](nf-engextcpp-extextension-getunnamedargu64.md) | The GetUnnamedArgU64 method returns the value of an unnamed expression argument from the command line used to invoke the current extension command. |
| [ExtExtension::HasArg method](nf-engextcpp-extextension-hasarg.md) | The HasArg method indicates whether a specified named argument is present in the command line used to invoke the current extension command. |
| [ExtExtension::HasCharArg method](nf-engextcpp-extextension-haschararg.md) | The HasCharArg method indicates whether a specified single-character named argument is present in the command line used to invoke the current extension command. |
| [ExtExtension::HasUnnamedArg method](nf-engextcpp-extextension-hasunnamedarg.md) | The HasUnnamedArg method indicates whether a specified unnamed argument is present in the command line used to invoke the current extension command. |
| [ExtExtension::Initialize method](nf-engextcpp-extextension-initialize.md) | The Initialize method is called by the engine to initialize an EngExtCpp extension library after loading it. |
| [ExtExtension::OnSessionAccessible method](nf-engextcpp-extextension-onsessionaccessible.md) | The OnSessionAccessible method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes accessible. |
| [ExtExtension::OnSessionActive method](nf-engextcpp-extextension-onsessionactive.md) | The OnSessionActive method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes active. |
| [ExtExtension::OnSessionInaccessible method](nf-engextcpp-extextension-onsessioninaccessible.md) | The OnSessionInaccessible method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes inaccessible. |
| [ExtExtension::OnSessionInactive method](nf-engextcpp-extextension-onsessioninactive.md) | The OnSessionInactive method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes inactive. |
| [ExtExtension::SetArg method](nf-engextcpp-extextension-setarg.md) | The SetArg method sets a named argument for the current extension command. |
| [ExtExtension::SetArgStr method](nf-engextcpp-extextension-setargstr.md) | The SetArgStr method sets a named string argument for the current expression command. |
| [ExtExtension::SetUnnamedArg method](nf-engextcpp-extextension-setunnamedarg.md) | The SetUnnamedArg method sets an unnamed argument for the current extension command. |
| [ExtExtension::SetUnnamedArgStr method](nf-engextcpp-extextension-setunnamedargstr.md) | The SetUnnamedArgStr method sets an unnamed string argument for the current extension command. |
| [ExtExtension::SetUnnamedArgU64 method](nf-engextcpp-extextension-setunnamedargu64.md) | The SetUnnamedArgU64 method sets the value of an unnamed expression argument for the current extension command. |
| [ExtExtension::Uninitialize method](nf-engextcpp-extextension-uninitialize.md) | The Uninitialize method is called by the engine to uninitialize an EngExtCpp extension library before it is unloaded. |
| [ExtRemoteData::Clear method](nf-engextcpp-extremotedata-clear.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::ExtRemoteData method](nf-engextcpp-extremotedata-extremotedata.md) | The ExtRemoteData constructor creates a new instance of the ExtRemoteData class. |
| [ExtRemoteData::GetBoolean method](nf-engextcpp-extremotedata-getboolean.md) | The GetBoolean method returns a Boolean version of the ExtRemoteData object, which represents the contents of the target's memory. |
| [ExtRemoteData::GetChar method](nf-engextcpp-extremotedata-getchar.md) | The GetChar method returns a CHAR version of the ExtRemoteData object, which represents the contents of the target's memory. |
| [ExtRemoteData::GetData method](nf-engextcpp-extremotedata-getdata.md) | The GetData method returns the contents of the target's memory, represented by the ExtRemoteData object. |
| [ExtRemoteData::GetDouble method](nf-engextcpp-extremotedata-getdouble.md) | The GetDouble method returns a double version of the ExtRemoteData object, which represents the contents of the target's memory. |
| [ExtRemoteData::GetFloat method](nf-engextcpp-extremotedata-getfloat.md) | The GetFloat method returns a float version of the ExtRemoteData object, which represents the contents of the target's memory. |
| [ExtRemoteData::GetLong method](nf-engextcpp-extremotedata-getlong.md) | The GetLong method returns a LONG version of the ExtRemoteData object, which represents the contents of the target's memory. |
| [ExtRemoteData::GetLong64 method](nf-engextcpp-extremotedata-getlong64.md) | The GetLong64 method returns a LONG64 version of the ExtRemoteData object, which represents the contents of the target's memory. |
| [ExtRemoteData::GetLongPtr method](nf-engextcpp-extremotedata-getlongptr.md) | The GetLongPtr method returns a signed integer version (extended to LONG64) of the ExtRemoteData object, which represents the contents of the target's memory. The size of the unsigned integer from the target is the same size as a pointer on the target. |
| [ExtRemoteData::GetPtr method](nf-engextcpp-extremotedata-getptr.md) | The GetPtr method returns a pointer from the target's memory version of the ExtRemoteData object, which represents the contents of the target's memory. The size of the unsigned integer from the target is the same size as a pointer on the target. |
| [ExtRemoteData::GetShort method](nf-engextcpp-extremotedata-getshort.md) | The GetShort method returns a SHORT version of the ExtRemoteData object, which represents the contents of the target's memory. |
| [ExtRemoteData::GetStdBool method](nf-engextcpp-extremotedata-getstdbool.md) | The GetStdBool method returns a bool version of the ExtRemoteData object, which represents the contents of the target's memory. |
| [ExtRemoteData::GetString method](nf-engextcpp-extremotedata-getstring.md) | The GetString method reads a null-terminated string from the target's memory. The string is located in the beginning of the region represented by the ExtRemoteData object. |
| [ExtRemoteData::GetUchar method](nf-engextcpp-extremotedata-getuchar.md) | The GetUChar method returns a UCHAR version of the ExtRemoteData object, which represents the contents of the target's memory. |
| [ExtRemoteData::GetUlong method](nf-engextcpp-extremotedata-getulong.md) | The GetUlong method returns a ULONG version of the ExtRemoteData object, which represents the contents of the target's memory. |
| [ExtRemoteData::GetUlong64 method](nf-engextcpp-extremotedata-getulong64.md) | The GetUlong64 method returns a ULONG64 version of the ExtRemoteData object, which represents the contents of the target's memory. |
| [ExtRemoteData::GetUlongPtr method](nf-engextcpp-extremotedata-getulongptr.md) | The GetUlongPtr method returns an unsigned integer version (extended to ULONG64) of the ExtRemoteData object, which represents the contents of the target's memory. |
| [ExtRemoteData::GetUshort method](nf-engextcpp-extremotedata-getushort.md) | The GetUshort method returns a USHORT version of the ExtRemoteData object, which represents the contents of the target's memory. |
| [ExtRemoteData::GetW32Bool method](nf-engextcpp-extremotedata-getw32bool.md) | The GetW32Bool method returns a BOOL version of the ExtRemoteData object, which represents the contents of the target's memory. |
| [ExtRemoteData::Read method](nf-engextcpp-extremotedata-read.md) | The Read method reads the contents of the target's memory, represented by the ExtRemoteData object, and then caches the data. |
| [ExtRemoteData::ReadBuffer method](nf-engextcpp-extremotedata-readbuffer.md) | The ReadBuffer method reads data from the target's memory. The data is located in the beginning of the region represented by the ExtRemoteData object. However, the size of the data can be different. |
| [ExtRemoteData::Set method](nf-engextcpp-extremotedata-set.md) | The Set method sets the region of the target's memory represented by the ExtRemoteData object. |
| [ExtRemoteData::SetBoolean method](nf-engextcpp-extremotedata-setboolean.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetChar method](nf-engextcpp-extremotedata-setchar.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetData method](nf-engextcpp-extremotedata-setdata.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetDouble method](nf-engextcpp-extremotedata-setdouble.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetFloat method](nf-engextcpp-extremotedata-setfloat.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetLong method](nf-engextcpp-extremotedata-setlong.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetLong64 method](nf-engextcpp-extremotedata-setlong64.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetLongPtr method](nf-engextcpp-extremotedata-setlongptr.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetPtr method](nf-engextcpp-extremotedata-setptr.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetShort method](nf-engextcpp-extremotedata-setshort.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetStdBool method](nf-engextcpp-extremotedata-setstdbool.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetUchar method](nf-engextcpp-extremotedata-setuchar.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetUlong method](nf-engextcpp-extremotedata-setulong.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetUlong64 method](nf-engextcpp-extremotedata-setulong64.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetUlongPtr method](nf-engextcpp-extremotedata-setulongptr.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetUshort method](nf-engextcpp-extremotedata-setushort.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::SetW32Bool method](nf-engextcpp-extremotedata-setw32bool.md) | The ExtRemoteData class provides a wrapper around a small section of a target's memory. ExtRemoteData automatically retrieves the memory and provides a number of convenience methods. |
| [ExtRemoteData::Write method](nf-engextcpp-extremotedata-write.md) | The Write method writes the data cached by the ExtRemoteData object to the region of memory on the target, represented by this object. |
| [ExtRemoteData::WriteBuffer method](nf-engextcpp-extremotedata-writebuffer.md) | The WriteBuffer method writes data to the target's memory. The data is located in the beginning of the region represented by the ExtRemoteData object. However, the size of the data can be different. |
| [ExtRemoteList::ExtRemoteList method](nf-engextcpp-extremotelist-extremotelist.md) | The ExtRemoteList class provides a wrapper around a singly-linked or doubly-linked list. The class contains methods that can be used to move both forward and backward through the list. |
| [ExtRemoteList::GetNodeOffset method](nf-engextcpp-extremotelist-getnodeoffset.md) | The GetNodeOffset method returns the address of the current list item. |
| [ExtRemoteList::HasNode method](nf-engextcpp-extremotelist-hasnode.md) | The HasNode method determines if there is a current item in the list iteration. |
| [ExtRemoteList::Next method](nf-engextcpp-extremotelist-next.md) | The Next method changes the current item to the next item in the list. |
| [ExtRemoteList::Prev method](nf-engextcpp-extremotelist-prev.md) | The Prev method changes the current item to the previous item in the list. |
| [ExtRemoteList::StartHead method](nf-engextcpp-extremotelist-starthead.md) | The StartHead method initializes the list for iterating forward starting at the head. |
| [ExtRemoteList::StartTail method](nf-engextcpp-extremotelist-starttail.md) | The StartTail method initializes the list for iterating backward, starting at the head. |
| [ExtRemoteTyped::ArrayElement method](nf-engextcpp-extremotetyped-arrayelement.md) | The ArrayElement method returns the typed data in the specified array element of the typed data represented by the ExtRemoteTyped object. |
| [ExtRemoteTyped::Clear method](nf-engextcpp-extremotetyped-clear.md) | The ExtRemoteTyped class provides the ability to manipulate typed data on the target. |
| [ExtRemoteTyped::Copy method](nf-engextcpp-extremotetyped-copy.md) | The Copy method sets the typed data represented by the ExtRemoteTyped object by copying the information from another object. |
| [ExtRemoteTyped::Dereference method](nf-engextcpp-extremotetyped-dereference.md) | The Dereference method returns the typed data that is pointed to by the typed data represented by this object. |
| [ExtRemoteTyped::ErtIoctl method](nf-engextcpp-extremotetyped-ertioctl.md) | The ExtRemoteTyped class provides the ability to manipulate typed data on the target. |
| [ExtRemoteTyped::Eval method](nf-engextcpp-extremotetyped-eval.md) | The Eval method returns typed data that is the result of evaluating an expression. |
| [ExtRemoteTyped::ExtRemoteTyped method](nf-engextcpp-extremotetyped-extremotetyped.md) | The ExtRemoteTyped constructors create a new instance of the ExtRemoteTyped class. |
| [ExtRemoteTyped::Field method](nf-engextcpp-extremotetyped-field.md) | The Field method returns the typed data for a member in the typed data that is represented by this object. |
| [ExtRemoteTyped::GetFieldOffset method](nf-engextcpp-extremotetyped-getfieldoffset.md) | The GetFieldOffset method returns the offset of a member from the base address of an instance of the type that is represented by this object. |
| [ExtRemoteTyped::GetPointerTo method](nf-engextcpp-extremotetyped-getpointerto.md) | The GetPointerTo method returns typed data that is a pointer to the typed data represented by this object. |
| [ExtRemoteTyped::GetSimpleValue method](nf-engextcpp-extremotetyped-getsimplevalue.md) | The ExtRemoteTyped class provides the ability to manipulate typed data on the target. |
| [ExtRemoteTyped::GetTypeFieldOffset method](nf-engextcpp-extremotetyped-gettypefieldoffset.md) | The GetTypeFieldOffset static method returns the offset of a member within a structure. |
| [ExtRemoteTyped::GetTypeName method](nf-engextcpp-extremotetyped-gettypename.md) | The GetTypeName method returns the type name of the typed data represented by this object. |
| [ExtRemoteTyped::GetTypeSize method](nf-engextcpp-extremotetyped-gettypesize.md) | The GetTypeSize method returns the size of the type represented by this object. |
| [ExtRemoteTyped::HasField method](nf-engextcpp-extremotetyped-hasfield.md) | The HasField method determines if the type of the data represented by this object contains the specified member. |
| [ExtRemoteTyped::OutFullValue method](nf-engextcpp-extremotetyped-outfullvalue.md) | The OutFullValue method prints the type and value of the typed data represented by this object. |
| [ExtRemoteTyped::OutSimpleValue method](nf-engextcpp-extremotetyped-outsimplevalue.md) | The OutSimpleValue method prints the value of the typed data represented by this object. |
| [ExtRemoteTyped::OutTypeDefinition method](nf-engextcpp-extremotetyped-outtypedefinition.md) | The OutTypeDefinition method prints the type of the typed data represented by this object. |
| [ExtRemoteTyped::OutTypeName method](nf-engextcpp-extremotetyped-outtypename.md) | The OutTypeName method prints the type name of the typed data represented by this object. |
| [ExtRemoteTyped::Release method](nf-engextcpp-extremotetyped-release.md) | The Release method releases any resources held by this object. |
| [ExtRemoteTyped::Set method](nf-engextcpp-extremotetyped-set.md) | The Set method sets the typed data represented by the ExtRemoteTyped object. |
| [ExtRemoteTyped::SetPrint method](nf-engextcpp-extremotetyped-setprint.md) | The SetPrint method sets the typed data represented by the ExtRemoteTyped object by formatting an expression and then evaluating that expression. |
| [ExtRemoteTyped::operator* method](nf-engextcpp-extremotetyped-operator.md) | The operator* overloaded operator returns the typed data that is pointed to by the typed data represented by this object. |
| [ExtRemoteTyped::operator= method](nf-engextcpp-extremotetyped-operator=.md) | The ExtRemoteTyped class provides the ability to manipulate typed data on the target. |
| [ExtRemoteTyped::operator[] method](nf-engextcpp-extremotetyped-operator[].md) | The operator[] overloaded operator returns the typed data in the specified array element of the typed data represented by this object. |
| [ExtRemoteTyped::~ExtRemoteTyped method](nf-engextcpp-extremotetyped-~extremotetyped.md) | The ExtRemoteTyped class provides the ability to manipulate typed data on the target. |
| [ExtRemoteTypedList::ExtRemoteTypedList method](nf-engextcpp-extremotetypedlist-extremotetypedlist.md) | The ExtRemoteTypedList class extends the ExtRemoteList class. The ExtRemoteTypedList class adds type information allowing each item in the list to be represented by an instance of the ExtRemoteTyped class. |
| [ExtRemoteTypedList::GetTypedNode method](nf-engextcpp-extremotetypedlist-gettypednode.md) | The GetTypedNode method returns the current list item. |
| [ExtRemoteTypedList::GetTypedNodePtr method](nf-engextcpp-extremotetypedlist-gettypednodeptr.md) | The GetTypedNodePtr method returns a pointer to the current list item. |
| [ExtRemoteTypedList::SetTypeAndLink method](nf-engextcpp-extremotetypedlist-settypeandlink.md) | The SetTypeAndLink method sets the type information for the typed list. |
| [ExtUnknownHolder::Set method](nf-engextcpp-extunknownholder-set.md) | The Set method sets the typed data represented by the ExtRemoteTyped object. |
| [ExtUnknownHolder::operator= method](nf-engextcpp-extunknownholder-operator=.md) | The operator= overloaded assignment operator sets the typed data represented by the ExtRemoteTyped object by copying the information from another object. |

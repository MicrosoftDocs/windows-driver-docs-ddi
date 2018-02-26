---
UID: NS:wdbgexts._FIELD_INFO
title: "_FIELD_INFO"
author: windows-driver-content
description: The FIELD_INFO structure is used by the IG_DUMP_SYMBOL_INFOIoctl operation to provide information about a member in a structure.
old-location: debugger\field_info.htm
old-project: debugger
ms.assetid: 627b14dc-9b13-464c-ba23-6e91bef2b940
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , *, *PFIELD_INFO, ,, D, E, F, FIELD_INFO, FIELD_INFO structure [Windows Debugging], I, L, N, O, P, PFIELD_INFO, PFIELD_INFO structure pointer [Windows Debugging], WdbgExts_Ref_4c79e59a-cd12-4ad9-affb-b7f0bd7689fb.xml, _, _FIELD_INFO, debugger.field_info, wdbgexts/FIELD_INFO, wdbgexts/PFIELD_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdbgexts.h
req.include-header: 
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
-	WdbgExts.h
apiname:
-	FIELD_INFO
product: Windows
targetos: Windows
req.typenames: FIELD_INFO, *PFIELD_INFO
req.product: Windows 10 or later.
---

# _FIELD_INFO structure


## -description


The <b>FIELD_INFO</b> structure is used by the <a href="..\wdbgexts\ns-wdbgexts-_sym_dump_param.md">IG_DUMP_SYMBOL_INFO</a>
<a href="..\wdbgexts\nc-wdbgexts-pwindbg_ioctl_routine.md">Ioctl</a> operation to provide information about a member in a structure.


## -syntax


````
typedef struct _FIELD_INFO {
  PUCHAR           fName;
  PUCHAR           printName;
  ULONG            size;
  ULONG            fOptions;
  ULONG64          address;
  union {
    PVOID fieldCallBack;
    PVOID pBuffer;
  };
  ULONG            TypeId;
  ULONG            FieldOffset;
  ULONG            BufferSize;
  struct _BitField {
    USHORT Position;
    USHORT Size;
  } BitField;
  ULONG            fPointer  :2;
  ULONG            fArray  :1;
  ULONG            fStruct  :1;
  ULONG            fConstant  :1;
  ULONG            Reserved  :27;
} FIELD_INFO, *PFIELD_INFO;
````


## -struct-fields




### -field fName

Specifies the name of the symbol's member to which this structure applies.  Submembers can be specified using the delimiters "<b>.</b>" and "<b>-&gt;</b>".  Unless DBG_DUMP_FIELD_FULL_NAME is set in <b>fOptions</b>, <b>fName</b> is considered to be the beginning of the member name.


### -field printName

Specifies an alternative name to use when printing the name of the member.  If <b>printName</b> is <b>NULL</b>, the actual name of the member is used when printing the name of the member.


### -field size

Receives the size in the target's memory, in bytes, of the member that is specified by <b>fName</b>.

If the member is an array, <b>size</b> specifies the number of elements in the array.


### -field fOptions

Specifies the flags that determine the behavior of the IG_DUMP_SYMBOL_INFO <b>Ioctl</b> operation.  For a description of these flags, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540429">DBG_DUMP_FIELD_XXX</a>.


### -field address

Receives the address in the target's memory of the member that is specified by <b>fName</b>.  If no address is supplied for the symbol type in SYM_DUMP_PARAM.<b>addr</b>, <b>address</b> receives the offset of the member relative to the beginning of an instance of the type.  For more information about SYM_DUMP_PARAM, see <a href="..\wdbgexts\ns-wdbgexts-_sym_dump_param.md">IG_DUMP_SYMBOL_INFO</a>.


### -field TypeId

Receives the identifier for the type of the member that is specified by <b>fName</b>.


### -field FieldOffset

Receives the offset of the member within the structure.


### -field BufferSize

Specifies the size, in bytes, of the <b>pBuffer</b> buffer.


### -field BitField

Receives information about bit fields in a structure.
      
	 



#### Position

Receives the start position of the bit field.  This is the number of bits from to the beginning of the structure to the bit field.



#### Size

Receives the size, in bits, of the bit field.


### -field _BitField

Receives information about bit fields in a structure.
      
	 



#### Position

Receives the start position of the bit field.  This is the number of bits from to the beginning of the structure to the bit field.



#### Size

Receives the size, in bits, of the bit field.


### -field fPointer

Receives a Boolean value that indicates whether the member is a pointer.  <b>fPointer</b> is <b>FALSE</b> if the member is not a pointer.  It is 1 if the member is a 32-bit pointer and 3 if the member is a 64-bit pointer.


### -field fArray

Receives a Boolean value that indicates whether the member is an array.  <b>fArray</b> is <b>FALSE</b> if the field is not an array and <b>TRUE</b> if it is.


### -field fStruct

Receives a Boolean value that indicates whether the member is a structure.  <b>fStruct</b> is <b>FALSE</b> if the member is not a structure and <b>TRUE</b> if it is.


### -field fConstant

Receives a Boolean value that indicates whether the member is a constant.  <b>fConstant</b> is <b>FALSE</b> if the member is not a constant and <b>TRUE</b> if it is.


### -field fStatic

 


### -field Reserved


#### - fieldCallBack

Specifies a <a href="..\wdbgexts\nc-wdbgexts-psym_dump_field_callback.md">PSYM_DUMP_FIELD_CALLBACK</a> callback function to be called with the information about the member that is specified by <b>fName</b>.  The callback function is passed a structure with the field information and the value of SYM_DUMP_PARAM.<b>context</b>.

No callback function is called if DBG_DUMP_FIELD_NO_CALLBACK_REQ is set in <b>fOptions</b>, <b>fieldCallBack</b> is <b>NULL</b>, or the <b>Options</b> member of the SYM_DUMP_PARAM structure passed to <b>Ioctl</b> does not have DBG_DUMP_CALL_FOR_EACH set.  If DBG_DUMP_FIELD_COPY_FIELD_DATA is set in <b>fOptions</b>, <b>fieldCallBack</b> is not used.


#### - pBuffer

Specifies a buffer to receive the value of the member specified by <b>fName</b>.  This member is only used if DBG_DUMP_FIELD_COPY_FIELD_DATA is set in <b>fOptions</b>.


## -remarks



When calling the <a href="..\wdbgexts\ns-wdbgexts-_sym_dump_param.md">IG_DUMP_SYMBOL_INFO</a>
<a href="..\wdbgexts\nc-wdbgexts-pwindbg_ioctl_routine.md">Ioctl</a> operation, the <b>fName</b> member of this structure should be set to the name of the symbol's member to which this structure applies and the <b>fOptions</b> member should reflect the desired functionality of the operation.  The other members are either optional, or are filled in by <b>Ioctl</b>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540429">DBG_DUMP_FIELD_XXX</a>



<a href="..\wdbgexts\ns-wdbgexts-_sym_dump_param.md">IG_DUMP_SYMBOL_INFO</a>



<a href="..\wdbgexts\nc-wdbgexts-pwindbg_ioctl_routine.md">Ioctl</a>



<a href="..\wdbgexts\nc-wdbgexts-psym_dump_field_callback.md">PSYM_DUMP_FIELD_CALLBACK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20FIELD_INFO structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


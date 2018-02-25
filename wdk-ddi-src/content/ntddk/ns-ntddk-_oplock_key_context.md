---
UID: NS:ntddk._OPLOCK_KEY_CONTEXT
title: "_OPLOCK_KEY_CONTEXT"
author: windows-driver-content
description: The OPLOCK_KEY_CONTEXT structure is returned from IoGetOplockKeyContextEx. This structure contains oplock keys for a specific file object.
old-location: ifsk\oplock_key_context.htm
old-project: ifsk
ms.assetid: E6A61B8F-CB43-4858-B5CF-32DD022A569E
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *POPLOCK_KEY_CONTEXT, ,, C, E, K, L, N, O, OPLOCK_KEY_CONTEXT, OPLOCK_KEY_CONTEXT structure [Installable File System Drivers], OPLOCK_KEY_FLAG_PARENT_KEY, OPLOCK_KEY_FLAG_TARGET_KEY, OPLOCK_KEY_VERSION_WIN7, OPLOCK_KEY_VERSION_WIN8, P, POPLOCK_KEY_CONTEXT, POPLOCK_KEY_CONTEXT structure pointer [Installable File System Drivers], T, X, Y, _, _OPLOCK_KEY_CONTEXT, ifsk.oplock_key_context, ntddk/OPLOCK_KEY_CONTEXT, ntddk/POPLOCK_KEY_CONTEXT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting in Windows 8.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	OPLOCK_KEY_CONTEXT
product: Windows
targetos: Windows
req.typenames: OPLOCK_KEY_CONTEXT, *POPLOCK_KEY_CONTEXT
---

# _OPLOCK_KEY_CONTEXT structure


## -description


The <b>OPLOCK_KEY_CONTEXT</b> structure is returned from <a href="..\ntddk\nf-ntddk-iogetoplockkeycontextex.md">IoGetOplockKeyContextEx</a>. This structure contains oplock keys for a specific file object.


## -syntax


````
typedef struct _OPLOCK_KEY_CONTEXT {
  ULONG Version  :8;
  ULONG Flags  :8;
  GUID  ParentOplockKey;
  GUID  TargetOplockKey;
} OPLOCK_KEY_CONTEXT, *POPLOCK_KEY_CONTEXT;
````


## -struct-fields




### -field Version

The oplock key version. The version is set to one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="OPLOCK_KEY_VERSION_WIN7"></a><a id="oplock_key_version_win7"></a><dl>
<dt><b>OPLOCK_KEY_VERSION_WIN7</b></dt>
</dl>
</td>
<td width="60%">
This is a Windows 7 oplock key.

</td>
</tr>
<tr>
<td width="40%"><a id="OPLOCK_KEY_VERSION_WIN8"></a><a id="oplock_key_version_win8"></a><dl>
<dt><b>OPLOCK_KEY_VERSION_WIN8</b></dt>
</dl>
</td>
<td width="60%">
This is a Windows 8 oplock key.

</td>
</tr>
</table>
 


### -field Flags

A set of flags that indicate the oplock key type. <b>Flags</b> is set to one or both of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="OPLOCK_KEY_FLAG_PARENT_KEY"></a><a id="oplock_key_flag_parent_key"></a><dl>
<dt><b>OPLOCK_KEY_FLAG_PARENT_KEY</b></dt>
</dl>
</td>
<td width="60%">
A valid oplock key is present in <b>ParentOplockKey.</b>

</td>
</tr>
<tr>
<td width="40%"><a id="OPLOCK_KEY_FLAG_TARGET_KEY"></a><a id="oplock_key_flag_target_key"></a><dl>
<dt><b>OPLOCK_KEY_FLAG_TARGET_KEY</b></dt>
</dl>
</td>
<td width="60%">
A valid oplock key is present in <b>TargetOplockKey.</b>

</td>
</tr>
</table>
 


### -field ParentOplockKey

A <b>GUID</b>  that represents the parent oplock  key value.


### -field TargetOplockKey

A <b>GUID</b>  that represents the target oplock  key value.


### -field Reserved

 




## -remarks



If an oplock is requested for a file during an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request, a file system that supports oplocks   will attach an oplock key context to the file object created. The oplock key  context is later available through a pointer to an <b>OPLOCK_KEY_CONTEXT</b> structure.  The <b>OPLOCK_KEY_CONTEXT</b> structure is returned from a call to <a href="..\ntddk\nf-ntddk-iogetoplockkeycontextex.md">IoGetOplockKeyContextEx</a>.




## -see-also

<a href="https://msdn.microsoft.com/5cbbfecc-2182-40f6-9f54-a8146c1f663f">Oplock Semantics</a>



<a href="..\ntddk\nf-ntddk-iogetoplockkeycontextex.md">IoGetOplockKeyContextEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406392">DUAL_OPLOCK_KEY_ECP_CONTEXT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20OPLOCK_KEY_CONTEXT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


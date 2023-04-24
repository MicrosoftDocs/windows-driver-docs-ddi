---
UID: NF:ntddk.RtlEnumerateGenericTableLikeADirectory
title: RtlEnumerateGenericTableLikeADirectory function (ntddk.h)
description: The RtlEnumerateGenericTableLikeADirectory routine returns the elements of a generic table, one-by-one, in collation order.
tech.root: ifsk
ms.date: 01/10/2023
keywords: ["RtlEnumerateGenericTableLikeADirectory function"]
ms.keywords: RtlEnumerateGenericTableLikeADirectory, RtlEnumerateGenericTableLikeADirectory routine [Installable File System Drivers], ifsk.rtlenumerategenerictablelikeadirectory, ntddk/RtlEnumerateGenericTableLikeADirectory, rtlref_7a5f2110-e171-4273-9928-9a8471f4e933.xml
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, FltKernel.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlEnumerateGenericTableLikeADirectory
 - ntddk/RtlEnumerateGenericTableLikeADirectory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlEnumerateGenericTableLikeADirectory
---

## -description

The **RtlEnumerateGenericTableLikeADirectory** routine returns the elements of a generic table, one-by-one, in collation order.

## -parameters

### -param Table [in]

A pointer to the Adelson-Velsky/Landis (AVL) table ([RTL_AVL_TABLE](./ns-ntddk-_rtl_avl_table.md)) that will be enumerated.

### -param MatchFunction [in, optional]

A match function that determines which entries to return. If not specified, all nodes are returned.

### -param MatchData [in, optional]

The data to pass to the match function.

### -param NextFlag [in]

If *RestartKey* is not **NULL**, a value of **TRUE** indicates that the enumeration will skip an element. If **FALSE** the enumeration resumes where it left off in the previous call to **RtlEnumerateGenericTableLikeADirectory**. If *RestartKey* is **NULL**, a value of **TRUE** instructs **RtlEnumerateGenericTableLikeADirectory** to return the next entry in the tree after the entry that matches the data in *Buffer*. A value of **FALSE** instructs **RtlEnumerateGenericTableLikeADirectory** to return the entry in the tree that matches the data in *Buffer*.

### -param RestartKey [in, out]

A value that determines where to begin or resume the enumeration of generic table elements. If *RestartKey* is **NULL**, the enumeration begins or resumes from the position that is described in *Buffer*. If not **NULL**, the enumeration resumes from the point that *RestartKey* indicates. On return, the *RestartKey* holds a value that indicates the place in the tree where the enumeration left off. On the next call to **RtlEnumerateGenericTableLikeADirectory** caller should pass the same value back in to inform **RtlEnumerateGenericTableLikeADirectory** where to resume the enumeration. The following code example illustrates how to do this:

```cpp
NextFlag = FALSE;
RestartKey = NULL;
DeleteCount = 0;
// Initialize Buffer for start/resume point
Buffer = ...
for (ptr = NULL; ptr != NULL;  ) {
  // Value returned in RestartKey will be passed back in
  // on following call (iteration):
  ptr = RtlEnumerateGenericTableLikeADirectory(
      &MyTable, NULL, NULL, TRUE, &RestartKey,
      &DeleteCount, &Buffer, sizeof(LONG) );
      ...
  // The value output in RestartKey will still be in
  // RestartKey when the
  // RtlEnumerationGenericTableLikeADirectory routine
  // is called in the next iteration of this loop.
  // This ensures that the enumeration will pick up
  // where it left off.
}
```

If a node is deleted from the tree between calls to **RtlEnumerateGenericTableLikeADirectory**, enumeration resumes from the position in the tree that is described in *Buffer*, no matter what the value of *RestartKey*.

### -param DeleteCount [in, out]

On output, a value that indicates the current count of entries deleted from the table. Caller must pass this value back in on the next call to **RtlEnumerateGenericTableLikeADirectory**. This value helps the **RtlEnumerateGenericTableLikeADirectory** routine determine if deletions from the table have occurred between calls to **RtlEnumerateGenericTableLikeADirectory**. If deletions have occurred, the enumeration resumes with the table entry that matches the data in *Buffer*, and not with the table entry indicated by *RestartKey*. If *RestartKey* is **NULL**, this parameter has no effect on the enumeration..

### -param Buffer [in]

A key expression that determines where to begin the enumeration, when *RestartKey* is **NULL**. Caller can pass in a saved key that matches a particular entry in the table and the enumeration will begin at the entry specified by the saved key, provided *RestartKey* is **NULL** and *NextFlag* is **FALSE**. To return the key that immediately follows a saved key, pass in the key here, set *RestartKey* to **NULL** and *NextFlag* to **TRUE**. If the saved key has been deleted, enumeration will begin with the next matched key.

## -returns

The **RtlEnumerateGenericTableLikeADirectory** routine returns a pointer to a user-defined structure that is associated with the next table element in the enumeration. If there are no more new elements to return the return value is **NULL**.

## -remarks

The **RtlEnumerateGenericTableLikeADirectory** routine provides a safe means to enumerate a generic table across intermixed insert and delete operations. Starting with the first matched key name, **RtlEnumerateGenericTableLikeADirectory** returns each name in the table exactly once, unless the name was inserted or deleted during the enumeration. When a key name is inserted or deleted during an enumeration (i.e. between calls to **RtlEnumerateGenericTableLikeADirectory**) it might or might not be included in the enumeration. Whether such names are included depends on the state of the name when **RtlEnumerateGenericTableLikeADirectory** processes the directory range in which the name is found.

There are four routines you can use to enumerate a generic table:

By default, the operating system uses splay trees to implement generic tables, but the **RtlEnumerateGenericTableLikeADirectory** routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including Ntddk.h:

```cpp
 #define RTL_USE_AVL_TABLES 0
```

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines.

Callers of **RtlEnumerateGenericTableLikeADirectory** must be running at IRQL <= APC_LEVEL if either of the following conditions holds:

- The caller-allocated memory at *Table* or at *Buffer* is pageable.

- The caller-supplied *MatchFunction* contains pageable code.

## -see-also

[RtlEnumerateGenericTable](./nf-ntddk-rtlenumerategenerictable.md)

[RtlEnumerateGenericTableWithoutSplaying](./nf-ntddk-rtlenumerategenerictablewithoutsplaying.md)

[RtlGetElementGenericTable](./nf-ntddk-rtlgetelementgenerictable.md)
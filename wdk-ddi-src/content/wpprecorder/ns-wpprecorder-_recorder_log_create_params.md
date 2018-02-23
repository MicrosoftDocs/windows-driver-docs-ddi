---
UID: NS:wpprecorder._RECORDER_LOG_CREATE_PARAMS
title: "_RECORDER_LOG_CREATE_PARAMS"
author: windows-driver-content
description: The RECORDER_LOG_CREATE_PARAMS structure is an input parameter to the WppRecorderLogCreate method.
old-location: devtest\recorder_log_create_params.htm
old-project: devtest
ms.assetid: 6BEB44C2-BB35-420F-B4A0-925FFAD7473C
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wpprecorder/RECORDER_LOG_CREATE_PARAMS, RECORDER_LOG_CREATE_PARAMS structure [Driver Development Tools], _RECORDER_LOG_CREATE_PARAMS, PRECORDER_LOG_CREATE_PARAMS, devtest.recorder_log_create_params, wpprecorder/PRECORDER_LOG_CREATE_PARAMS, PRECORDER_LOG_CREATE_PARAMS structure pointer [Driver Development Tools], RECORDER_LOG_CREATE_PARAMS, *PRECORDER_LOG_CREATE_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wpprecorder.h
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
-	Wpprecorder.h
apiname:
-	RECORDER_LOG_CREATE_PARAMS
product: Windows
targetos: Windows
req.typenames: RECORDER_LOG_CREATE_PARAMS, *PRECORDER_LOG_CREATE_PARAMS
req.product: Windows 10 or later.
---

# _RECORDER_LOG_CREATE_PARAMS structure


## -description


The <b>RECORDER_LOG_CREATE_PARAMS</b> structure is an input parameter to the <a href="..\wpprecorder\nf-wpprecorder-imp_wpprecorderlogcreate.md">WppRecorderLogCreate</a> method. 


## -syntax


````
typedef struct _RECORDER_LOG_CREATE_PARAMS {
  ULONG     Size;
  ULONG     LogTag;
  ULONG     TotalBufferSize;
  ULONG     ErrorPartitionSize;
  ULONG_PTR LogIdentifierAppendValue;
  BOOLEAN   LogIdentifierAppendValueSet;
  ULONG     LogIdentifierSize;
            LogIdentifier[RECORDER_LOG_IDENTIFIER_MAX_CHARS];
} RECORDER_LOG_CREATE_PARAMS, *PRECORDER_LOG_CREATE_PARAMS;
````


## -struct-fields




### -field Size

 Size of this structure.


### -field LogTag

 Optional tag to associate with the allocated memory of the log.


### -field TotalBufferSize

Size in bytes for the log area.


### -field ErrorPartitionSize

 The number of bytes out  of <b>TotalBufferSize</b> used to log error messages. Zero indicates no error partition.


### -field LogIdentifierAppendValue

 Number/pointer to append to log identifier.


### -field LogIdentifierAppendValueSet

 Specifies whether <b>LogIdentifierAppendValue</b> has been set.


### -field LogIdentifierSize

 Size of <b>LogIdentifier</b> field, in bytes (according to client's definition).


### -field LogIdentifier

Identifier to print when debug messages are merged. Lives at end of structure so that, if at some point clients have different definitions of the array size, it remains simple to read the rest of the structure.


## -see-also

<a href="..\wpprecorder\nf-wpprecorder-recorder_log_create_params_init.md">RECORDER_LOG_CREATE_PARAMS_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20RECORDER_LOG_CREATE_PARAMS structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


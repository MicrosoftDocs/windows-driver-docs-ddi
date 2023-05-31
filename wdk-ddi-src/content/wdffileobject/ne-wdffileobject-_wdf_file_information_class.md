---
UID: NE:wdffileobject._WDF_FILE_INFORMATION_CLASS
title: _WDF_FILE_INFORMATION_CLASS (wdffileobject.h)
description: The WDF_FILE_INFORMATION_CLASS enumeration identifies the types of file information that a driver can obtain or set.
old-location: wdf\wdf_file_information_class.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_FILE_INFORMATION_CLASS enumeration"]
ms.keywords: "*PWDF_FILE_INFORMATION_CLASS, PWDF_FILE_INFORMATION_CLASS, PWDF_FILE_INFORMATION_CLASS enumeration pointer, WDF_FILE_INFORMATION_CLASS, WDF_FILE_INFORMATION_CLASS enumeration, WdfFileInformationAccess, WdfFileInformationAlignment, WdfFileInformationAll, WdfFileInformationAllocation, WdfFileInformationAlternateName, WdfFileInformationAttributeCache, WdfFileInformationAttributeTag, WdfFileInformationBasic, WdfFileInformationBothDirectory, WdfFileInformationCompletion, WdfFileInformationCompression, WdfFileInformationDirectory, WdfFileInformationDisposition, WdfFileInformationEa, WdfFileInformationEndOfFile, WdfFileInformationFullDirectory, WdfFileInformationFullEa, WdfFileInformationHardLink, WdfFileInformationIdBothDirectory, WdfFileInformationIdFullDirectory, WdfFileInformationIdGlobalTxDirectory, WdfFileInformationInternal, WdfFileInformationIoCompletionNotification, WdfFileInformationIoPriorityHint, WdfFileInformationIoStatusBlockRange, WdfFileInformationIsRemoteDevice, WdfFileInformationLink, WdfFileInformationMailslotQuery, WdfFileInformationMailslotSet, WdfFileInformationMaximum, WdfFileInformationMode, WdfFileInformationMoveCluster, WdfFileInformationName, WdfFileInformationNames, WdfFileInformationNetworkOpen, WdfFileInformationNetworkPhysicalName, WdfFileInformationNormalizedName, WdfFileInformationObjectId, WdfFileInformationPipe, WdfFileInformationPipeLocal, WdfFileInformationPipeRemote, WdfFileInformationPosition, WdfFileInformationProcessIdsUsingFile, WdfFileInformationQuota, WdfFileInformationRename, WdfFileInformationReparsePoint, WdfFileInformationSfioReserve, WdfFileInformationSfioVolume, WdfFileInformationShortName, WdfFileInformationStandard, WdfFileInformationStream, WdfFileInformationTracking, WdfFileInformationValidDataLength, _WDF_FILE_INFORMATION_CLASS, umdf.wdf_file_information_class, umdfstructs_ffc1a1df-4784-4dd7-8bc7-f134554834bc.xml, wdf.wdf_file_information_class, wdffileobject/PWDF_FILE_INFORMATION_CLASS, wdffileobject/WDF_FILE_INFORMATION_CLASS, wdffileobject/WdfFileInformationAccess, wdffileobject/WdfFileInformationAlignment, wdffileobject/WdfFileInformationAll, wdffileobject/WdfFileInformationAllocation, wdffileobject/WdfFileInformationAlternateName, wdffileobject/WdfFileInformationAttributeCache, wdffileobject/WdfFileInformationAttributeTag, wdffileobject/WdfFileInformationBasic, wdffileobject/WdfFileInformationBothDirectory, wdffileobject/WdfFileInformationCompletion, wdffileobject/WdfFileInformationCompression, wdffileobject/WdfFileInformationDirectory, wdffileobject/WdfFileInformationDisposition, wdffileobject/WdfFileInformationEa, wdffileobject/WdfFileInformationEndOfFile, wdffileobject/WdfFileInformationFullDirectory, wdffileobject/WdfFileInformationFullEa, wdffileobject/WdfFileInformationHardLink, wdffileobject/WdfFileInformationIdBothDirectory, wdffileobject/WdfFileInformationIdFullDirectory, wdffileobject/WdfFileInformationIdGlobalTxDirectory, wdffileobject/WdfFileInformationInternal, wdffileobject/WdfFileInformationIoCompletionNotification, wdffileobject/WdfFileInformationIoPriorityHint, wdffileobject/WdfFileInformationIoStatusBlockRange, wdffileobject/WdfFileInformationIsRemoteDevice, wdffileobject/WdfFileInformationLink, wdffileobject/WdfFileInformationMailslotQuery, wdffileobject/WdfFileInformationMailslotSet, wdffileobject/WdfFileInformationMaximum, wdffileobject/WdfFileInformationMode, wdffileobject/WdfFileInformationMoveCluster, wdffileobject/WdfFileInformationName, wdffileobject/WdfFileInformationNames, wdffileobject/WdfFileInformationNetworkOpen, wdffileobject/WdfFileInformationNetworkPhysicalName, wdffileobject/WdfFileInformationNormalizedName, wdffileobject/WdfFileInformationObjectId, wdffileobject/WdfFileInformationPipe, wdffileobject/WdfFileInformationPipeLocal, wdffileobject/WdfFileInformationPipeRemote, wdffileobject/WdfFileInformationPosition, wdffileobject/WdfFileInformationProcessIdsUsingFile, wdffileobject/WdfFileInformationQuota, wdffileobject/WdfFileInformationRename, wdffileobject/WdfFileInformationReparsePoint, wdffileobject/WdfFileInformationSfioReserve, wdffileobject/WdfFileInformationSfioVolume, wdffileobject/WdfFileInformationShortName, wdffileobject/WdfFileInformationStandard, wdffileobject/WdfFileInformationStream, wdffileobject/WdfFileInformationTracking, wdffileobject/WdfFileInformationValidDataLength, wudfddi_types/PWDF_FILE_INFORMATION_CLASS, wudfddi_types/WDF_FILE_INFORMATION_CLASS, wudfddi_types/WdfFileInformationAccess, wudfddi_types/WdfFileInformationAlignment, wudfddi_types/WdfFileInformationAll, wudfddi_types/WdfFileInformationAllocation, wudfddi_types/WdfFileInformationAlternateName, wudfddi_types/WdfFileInformationAttributeCache, wudfddi_types/WdfFileInformationAttributeTag, wudfddi_types/WdfFileInformationBasic, wudfddi_types/WdfFileInformationBothDirectory, wudfddi_types/WdfFileInformationCompletion, wudfddi_types/WdfFileInformationCompression, wudfddi_types/WdfFileInformationDirectory, wudfddi_types/WdfFileInformationDisposition, wudfddi_types/WdfFileInformationEa, wudfddi_types/WdfFileInformationEndOfFile, wudfddi_types/WdfFileInformationFullDirectory, wudfddi_types/WdfFileInformationFullEa, wudfddi_types/WdfFileInformationHardLink, wudfddi_types/WdfFileInformationIdBothDirectory, wudfddi_types/WdfFileInformationIdFullDirectory, wudfddi_types/WdfFileInformationIdGlobalTxDirectory, wudfddi_types/WdfFileInformationInternal, wudfddi_types/WdfFileInformationIoCompletionNotification, wudfddi_types/WdfFileInformationIoPriorityHint, wudfddi_types/WdfFileInformationIoStatusBlockRange, wudfddi_types/WdfFileInformationIsRemoteDevice, wudfddi_types/WdfFileInformationLink, wudfddi_types/WdfFileInformationMailslotQuery, wudfddi_types/WdfFileInformationMailslotSet, wudfddi_types/WdfFileInformationMaximum, wudfddi_types/WdfFileInformationMode, wudfddi_types/WdfFileInformationMoveCluster, wudfddi_types/WdfFileInformationName, wudfddi_types/WdfFileInformationNames, wudfddi_types/WdfFileInformationNetworkOpen, wudfddi_types/WdfFileInformationNetworkPhysicalName, wudfddi_types/WdfFileInformationNormalizedName, wudfddi_types/WdfFileInformationObjectId, wudfddi_types/WdfFileInformationPipe, wudfddi_types/WdfFileInformationPipeLocal, wudfddi_types/WdfFileInformationPipeRemote, wudfddi_types/WdfFileInformationPosition, wudfddi_types/WdfFileInformationProcessIdsUsingFile, wudfddi_types/WdfFileInformationQuota, wudfddi_types/WdfFileInformationRename, wudfddi_types/WdfFileInformationReparsePoint, wudfddi_types/WdfFileInformationSfioReserve, wudfddi_types/WdfFileInformationSfioVolume, wudfddi_types/WdfFileInformationShortName, wudfddi_types/WdfFileInformationStandard, wudfddi_types/WdfFileInformationStream, wudfddi_types/WdfFileInformationTracking, wudfddi_types/WdfFileInformationValidDataLength"
req.header: wdffileobject.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
f1_keywords:
 - _WDF_FILE_INFORMATION_CLASS
 - wdffileobject/_WDF_FILE_INFORMATION_CLASS
 - PWDF_FILE_INFORMATION_CLASS
 - wdffileobject/PWDF_FILE_INFORMATION_CLASS
 - WDF_FILE_INFORMATION_CLASS
 - wdffileobject/WDF_FILE_INFORMATION_CLASS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wudfddi_types.h
 - Wdffileobject.h
api_name:
 - _WDF_FILE_INFORMATION_CLASS
 - PWDF_FILE_INFORMATION_CLASS
 - WDF_FILE_INFORMATION_CLASS
---

# _WDF_FILE_INFORMATION_CLASS enumeration (wdffileobject.h)


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WDF_FILE_INFORMATION_CLASS</b> enumeration identifies the types of file information that a driver can obtain or set.

## -enum-fields

### -field WdfFileInformationDirectory:1

### -field WdfFileInformationFullDirectory:2

### -field WdfFileInformationBothDirectory:3

### -field WdfFileInformationBasic:4

### -field WdfFileInformationStandard:5

### -field WdfFileInformationInternal:6

### -field WdfFileInformationEa:7

### -field WdfFileInformationAccess:8

### -field WdfFileInformationName:9

### -field WdfFileInformationRename:10

### -field WdfFileInformationLink:11

### -field WdfFileInformationNames:12

### -field WdfFileInformationDisposition:13

### -field WdfFileInformationPosition:14

### -field WdfFileInformationFullEa:15

### -field WdfFileInformationMode:16

### -field WdfFileInformationAlignment:17

### -field WdfFileInformationAll:18

### -field WdfFileInformationAllocation:19

### -field WdfFileInformationEndOfFile:20

### -field WdfFileInformationAlternateName:21

### -field WdfFileInformationStream:22

### -field WdfFileInformationPipe:23

### -field WdfFileInformationPipeLocal:24

### -field WdfFileInformationPipeRemote:25

### -field WdfFileInformationMailslotQuery:26

### -field WdfFileInformationMailslotSet:27

### -field WdfFileInformationCompression:28

### -field WdfFileInformationObjectId:29

### -field WdfFileInformationCompletion:30

### -field WdfFileInformationMoveCluster:31

### -field WdfFileInformationQuota:32

### -field WdfFileInformationReparsePoint:33

### -field WdfFileInformationNetworkOpen:34

### -field WdfFileInformationAttributeTag:35

### -field WdfFileInformationTracking:36

### -field WdfFileInformationIdBothDirectory:37

### -field WdfFileInformationIdFullDirectory:38

### -field WdfFileInformationValidDataLength:39

### -field WdfFileInformationShortName:40

### -field WdfFileInformationIoCompletionNotification:41

### -field WdfFileInformationIoStatusBlockRange:42

### -field WdfFileInformationIoPriorityHint:43

### -field WdfFileInformationSfioReserve:44

### -field WdfFileInformationSfioVolume:45

### -field WdfFileInformationHardLink:46

### -field WdfFileInformationProcessIdsUsingFile:47

### -field WdfFileInformationNormalizedName:48

### -field WdfFileInformationNetworkPhysicalName:49

### -field WdfFileInformationIdGlobalTxDirectory:50

### -field WdfFileInformationIsRemoteDevice:51

### -field WdfFileInformationAttributeCache:52

### -field WdfFileInformationMaximum:

## -remarks

The <b>WDF_FILE_INFORMATION_CLASS</b> enumeration is used as an input value to <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-getqueryinformationparameters">IWDFIoRequest2::GetQueryInformationParameters</a> and as an output value from <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-getsetinformationparameters">IWDFIoRequest2::GetSetInformationParameters</a>.

For most values that the <b>WDF_FILE_INFORMATION_CLASS</b> enumeration defines, the wdm.h or ntifs.h header file defines a FILE_XXXX_INFORMATION-named structure that the driver can use when obtaining or setting the file information.

For more information about the enumeration value and associated structures, see the description of the <i>FileInformationClass</i> parameter of <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a> and <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-getqueryinformationparameters">IWDFIoRequest2::GetQueryInformationParameters</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-getsetinformationparameters">IWDFIoRequest2::GetSetInformationParameters</a>


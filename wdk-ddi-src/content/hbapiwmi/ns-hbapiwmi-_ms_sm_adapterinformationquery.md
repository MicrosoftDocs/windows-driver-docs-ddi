---
UID: NS:hbapiwmi._MS_SM_AdapterInformationQuery
title: "_MS_SM_AdapterInformationQuery"
author: windows-driver-content
description: The MS_SM_AdapterInformationQuery structure is used by a WMI provider to expose attributes that are associated with a SAS adapter.
old-location: storage\ms_sm_adapterinformationquery.htm
old-project: storage
ms.assetid: 81c05f47-e75a-4d67-8e77-33ebe1750c67
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ms_sm_adapterinformationquery, hbapiwmi/MS_SM_AdapterInformationQuery, hbapiwmi/PMS_SM_AdapterInformationQuery, PMS_SM_AdapterInformationQuery, _MS_SM_AdapterInformationQuery, MS_SM_AdapterInformationQuery structure [Storage Devices], PMS_SM_AdapterInformationQuery structure pointer [Storage Devices], structs-Fibre_feda1502-e2b9-4392-a3bd-9c10ab0fab52.xml, *PMS_SM_AdapterInformationQuery, MS_SM_AdapterInformationQuery
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
-	hbapiwmi.h
apiname:
-	MS_SM_AdapterInformationQuery
product: Windows
targetos: Windows
req.typenames: MS_SM_AdapterInformationQuery, *PMS_SM_AdapterInformationQuery
---

# _MS_SM_AdapterInformationQuery structure


## -description


The MS_SM_AdapterInformationQuery structure is used by a WMI provider to expose attributes that are associated with a SAS adapter.


## -syntax


````
typedef struct _MS_SM_AdapterInformationQuery {
  ULONGLONG UniqueAdapterId;
  ULONG     HBAStatus;
  ULONG     NumberOfPorts;
  ULONG     VendorSpecificID;
  WCHAR     Manufacturer[64 + 1];
  WCHAR     SerialNumber[64 + 1];
  WCHAR     Model[256 + 1];
  WCHAR     ModelDescription[256 + 1];
  WCHAR     HardwareVersion[256 + 1];
  WCHAR     DriverVersion[256 + 1];
  WCHAR     OptionROMVersion[256 + 1];
  WCHAR     FirmwareVersion[256 + 1];
  WCHAR     DriverName[256 + 1];
  WCHAR     HBASymbolicName[256 + 1];
  WCHAR     RedundantOptionROMVersion[256 + 1];
  WCHAR     RedundantFirmwareVersion[256 + 1];
  WCHAR     MfgDomain[256 + 1];
} MS_SM_AdapterInformationQuery, *PMS_SM_AdapterInformationQuery;
````


## -struct-fields




#### - UniqueAdapterId

The unique adapter ID.


#### - HBAStatus

The status of the operation.


#### - NumberOfPorts

The number of ports on the HBA.


#### - VendorSpecificID

A vendor-specific ID.


#### - Manufacturer

An ASCII string that is 64 bytes or fewer in length and that identifies the name of the manufacturer of the HBA.


#### - SerialNumber

An ASCII string that is 64 bytes or fewer in length and that identifies the serial number of the HBA.


#### - Model

An ASCII string that is 256 bytes or fewer in length and that identifies the vendor-specific name of the HBA model.


#### - ModelDescription

An ASCII string that is 256 bytes or fewer in length and that indicates the model description.


#### - HardwareVersion

An ASCII string that is 256 bytes or fewer in length and that indicates the vendor-specific hardware revision level of the HBA.


#### - DriverVersion

An ASCII string that is 256 bytes or fewer in length and that indicates the vendor-specific version of the HBA miniport driver.


#### - OptionROMVersion

An ASCII string that is 256 bytes or fewer in length and that indicates the vendor-specific option ROM or BIOS version of the HBA.


#### - FirmwareVersion

An ASCII string that is 256 bytes or fewer in length and that indicates the vendor-specific firmware version of the HBA.


#### - DriverName

An ASCII string that is 256 bytes or fewer in length and that indicates the file name for the driver binary file.


#### - HBASymbolicName

An ASCII string that is 256 bytes or fewer in length and that indicates the symbolic name for the fibre channel node.


#### - RedundantOptionROMVersion

An ASCII string that is 256 bytes or fewer in length and that indicates the vendor-specific option ROM or BIOS version of the HBA.


#### - RedundantFirmwareVersion

An ASCII string that is 256 bytes or fewer in length and that indicates the vendor-specific firmware version of the HBA.


#### - MfgDomain

The name of the HBA manufacturer.


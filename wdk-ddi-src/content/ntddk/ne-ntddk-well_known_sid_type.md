---
UID: NE:ntddk.__unnamed_enum_0
title: WELL_KNOWN_SID_TYPE (ntddk.h)
description: A list of commonly used security identifiers (SIDs). Programs can pass these values to the **CreateWellKnownSid** function to create a SID from this list. For information about these values, see [WELL_KNOWN_SID_TYPE](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createwellknownsid).
tech.root: ifsk
ms.date: 10/19/2018
keywords: ["WELL_KNOWN_SID_TYPE enumeration"]
ms.keywords: WELL_KNOWN_SID_TYPE, WELL_KNOWN_SID_TYPE
req.header: ntddk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: WELL_KNOWN_SID_TYPE
targetos: Windows
f1_keywords:
 - WELL_KNOWN_SID_TYPE
 - ntddk/WELL_KNOWN_SID_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - WELL_KNOWN_SID_TYPE
---

# WELL_KNOWN_SID_TYPE enumeration


## -description

A list of commonly used security identifiers (SIDs). Programs can pass these values to the **CreateWellKnownSid** function to create a SID from this list. For information about these values, see [WELL_KNOWN_SID_TYPE](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createwellknownsid).

## -enum-fields

### -field WinNullSid : 

### -field WinWorldSid : 

### -field WinLocalSid : 

### -field WinCreatorOwnerSid : 

### -field WinCreatorGroupSid : 

### -field WinCreatorOwnerServerSid : 

### -field WinCreatorGroupServerSid : 

### -field WinNtAuthoritySid : 

### -field WinDialupSid : 

### -field WinNetworkSid : 

### -field WinBatchSid : 

### -field WinInteractiveSid : 

### -field WinServiceSid : 

### -field WinAnonymousSid : 

### -field WinProxySid : 

### -field WinEnterpriseControllersSid : 

### -field WinSelfSid : 

### -field WinAuthenticatedUserSid : 

### -field WinRestrictedCodeSid : 

### -field WinTerminalServerSid : 

### -field WinRemoteLogonIdSid : 

### -field WinLogonIdsSid : 

### -field WinLocalSystemSid : 

### -field WinLocalServiceSid : 

### -field WinNetworkServiceSid : 

### -field WinBuiltinDomainSid : 

### -field WinBuiltinAdministratorsSid : 

### -field WinBuiltinUsersSid : 

### -field WinBuiltinGuestsSid : 

### -field WinBuiltinPowerUsersSid : 

### -field WinBuiltinAccountOperatorsSid : 

### -field WinBuiltinSystemOperatorsSid : 

### -field WinBuiltinPrintOperatorsSid : 

### -field WinBuiltinBackupOperatorsSid : 

### -field WinBuiltinReplicatorSid : 

### -field WinBuiltinPreWindows2000CompatibleAccessSid : 

### -field WinBuiltinRemoteDesktopUsersSid : 

### -field WinBuiltinNetworkConfigurationOperatorsSid : 

### -field WinAccountAdministratorSid : 

### -field WinAccountGuestSid : 

### -field WinAccountKrbtgtSid : 

### -field WinAccountDomainAdminsSid : 

### -field WinAccountDomainUsersSid : 

### -field WinAccountDomainGuestsSid : 

### -field WinAccountComputersSid : 

### -field WinAccountControllersSid : 

### -field WinAccountCertAdminsSid : 

### -field WinAccountSchemaAdminsSid : 

### -field WinAccountEnterpriseAdminsSid : 

### -field WinAccountPolicyAdminsSid : 

### -field WinAccountRasAndIasServersSid : 

### -field WinNTLMAuthenticationSid : 

### -field WinDigestAuthenticationSid : 

### -field WinSChannelAuthenticationSid : 

### -field WinThisOrganizationSid : 

### -field WinOtherOrganizationSid : 

### -field WinBuiltinIncomingForestTrustBuildersSid : 

### -field WinBuiltinPerfMonitoringUsersSid : 

### -field WinBuiltinPerfLoggingUsersSid : 

### -field WinBuiltinAuthorizationAccessSid : 

### -field WinBuiltinTerminalServerLicenseServersSid : 

### -field WinBuiltinDCOMUsersSid : 

### -field WinBuiltinIUsersSid : 

### -field WinIUserSid : 

### -field WinBuiltinCryptoOperatorsSid : 

### -field WinUntrustedLabelSid : 

### -field WinLowLabelSid : 

### -field WinMediumLabelSid : 

### -field WinHighLabelSid : 

### -field WinSystemLabelSid : 

### -field WinWriteRestrictedCodeSid : 

### -field WinCreatorOwnerRightsSid : 

### -field WinCacheablePrincipalsGroupSid : 

### -field WinNonCacheablePrincipalsGroupSid : 

### -field WinEnterpriseReadonlyControllersSid : 

### -field WinAccountReadonlyControllersSid : 

### -field WinBuiltinEventLogReadersGroup : 

### -field WinNewEnterpriseReadonlyControllersSid : 

### -field WinBuiltinCertSvcDComAccessGroup : 

### -field WinMediumPlusLabelSid : 

### -field WinLocalLogonSid : 

### -field WinConsoleLogonSid : 

### -field WinThisOrganizationCertificateSid : 

### -field WinApplicationPackageAuthoritySid : 

### -field WinBuiltinAnyPackageSid : 

### -field WinCapabilityInternetClientSid : 

### -field WinCapabilityInternetClientServerSid : 

### -field WinCapabilityPrivateNetworkClientServerSid : 

### -field WinCapabilityPicturesLibrarySid : 

### -field WinCapabilityVideosLibrarySid : 

### -field WinCapabilityMusicLibrarySid : 

### -field WinCapabilityDocumentsLibrarySid : 

### -field WinCapabilitySharedUserCertificatesSid : 

### -field WinCapabilityEnterpriseAuthenticationSid : 

### -field WinCapabilityRemovableStorageSid : 

### -field WinBuiltinRDSRemoteAccessServersSid : 

### -field WinBuiltinRDSEndpointServersSid : 

### -field WinBuiltinRDSManagementServersSid : 

### -field WinUserModeDriversSid : 

### -field WinBuiltinHyperVAdminsSid : 

### -field WinAccountCloneableControllersSid : 

### -field WinBuiltinAccessControlAssistanceOperatorsSid : 

### -field WinBuiltinRemoteManagementUsersSid : 

### -field WinAuthenticationAuthorityAssertedSid : 

### -field WinAuthenticationServiceAssertedSid : 

### -field WinLocalAccountSid : 

### -field WinLocalAccountAndAdministratorSid : 

### -field WinAccountProtectedUsersSid : 

### -field WinCapabilityAppointmentsSid : 

### -field WinCapabilityContactsSid : 

### -field WinAccountDefaultSystemManagedSid : 

### -field WinBuiltinDefaultSystemManagedGroupSid : 

### -field WinBuiltinStorageReplicaAdminsSid : 

### -field WinAccountKeyAdminsSid : 

### -field WinAccountEnterpriseKeyAdminsSid : 

### -field WinAuthenticationKeyTrustSid : 

### -field WinAuthenticationKeyPropertyMFASid : 

### -field WinAuthenticationKeyPropertyAttestationSid : 

### -field WinAuthenticationFreshKeyAuthSid : 

### -field WinBuiltinDeviceOwnersSid : 

## -remarks

## -see-also

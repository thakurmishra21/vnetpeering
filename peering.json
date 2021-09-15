Param($pClientId, $pKey,$pTenantId,$pSubscriptionId,$pWorkspaceName,$saPath)
Install-Module -Name Az.Synapse -force

$clientID = $pClientId
$key = $pKey
$SecurePassword = $key | ConvertTo-SecureString -AsPlainText -Force
$cred = new-object -typename System.Management.Automation.PSCredential -argumentlist $clientID, $SecurePassword
$tenantID = $pTenantId

Connect-AzAccount -Credential $cred -TenantId $tenantID -ServicePrincipal
Select-AzSubscription -SubscriptionId $pSubscriptionId

Set-AzSynapseSqlAuditSetting -WorkspaceName $pWorkspaceName -BlobStorageTargetState Enabled -StorageAccountResourceId $saPath -StorageKeyType Primary
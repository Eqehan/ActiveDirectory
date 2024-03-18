Import-Module ActiveDirectory
$Users = Import-Csv C:\Praktiga.csv -Delimiter ";"
echo $Users |Format-Table
$Pswd = ConvertTo-SecureString "Pswd123" -AsPlainText -Force

ForEach($user in $Users) {
    $fname = $User.'First Name'
    $lname = $user.'Last Name'
    $title = $user.'Job Title'
    $tel = $user.'Telephone'
    $email = $user.'Email Adress'
    $OUpath = $user.'OU'

    New-ADUser -Name "$fname $lname" -GivenName $fname -Surname $lname -UserPrincipalName "$fname.$lname" -Path $OUpath -OfficePhone $tel -EmailAddress $email -AccountPassword $Pswd -ChangePasswordAtLogon $true -Enabled $true

    echo " $fname $lname kullanicisinin verileri AD üzerine yazilmistir."
}
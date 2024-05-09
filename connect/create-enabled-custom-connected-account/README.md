# Create an Enabled Custom Connected Account (UK) 

This collection is made of three steps: 

## Step 1 Create an Custom Connected Account

```
curl --location 'https://api.stripe.com/v1/accounts' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Bearer sk_*****' \
--data-urlencode 'business_profile%5Bmcc%5D=5734' \
--data-urlencode 'business_profile%5Bname%5D=Connected Account' \
--data-urlencode 'business_profile%5Bproduct_description%5D=Product Description' \
--data-urlencode 'business_type=company' \
--data-urlencode 'company%5Baddress%5D%5Bcity%5D=London' \
--data-urlencode 'company%5Baddress%5D%5Bcountry%5D=GB' \
--data-urlencode 'company%5Baddress%5D%5Bline1%5D=21 Old Street' \
--data-urlencode 'company%5Baddress%5D%5Bpostal_code%5D=EC1M 7AD' \
--data-urlencode 'company%5Baddress%5D%5Bstate%5D=null' \
--data-urlencode 'company%5Bname%5D=Connected Account (DBA)' \
--data-urlencode 'company%5Bphone%5D=+447400123456' \
--data-urlencode 'company%5Btax_id%5D=12345678' \
--data-urlencode 'default_currency=gbp' \
--data-urlencode 'type=custom' \
--data-urlencode 'capabilities%5Bcard_payments%5D%5Brequested%5D=true' \
--data-urlencode 'capabilities%5Btransfers%5D%5Brequested%5D=true' \
--data-urlencode 'tos_acceptance%5Bdate%5D=1609798905' \
--data-urlencode 'tos_acceptance%5Bip%5D=8.8.8.8'
```

## Create a person

```
curl --location 'https://api.stripe.com/v1/accounts/{{ACCOUNT_ID}}/persons' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Bearer sk_*****' \
--data-urlencode 'first_name=John' \
--data-urlencode 'last_name=Doe' \
--data-urlencode 'address%5Bcity%5D=London' \
--data-urlencode 'address%5Bcountry%5D=GB' \
--data-urlencode 'address%5Bline1%5D=21 Old Street' \
--data-urlencode 'address%5Bpostal_code%5D=EC1M 7AD' \
--data-urlencode 'dob%5Bday%5D=1' \
--data-urlencode 'dob%5Bmonth%5D=10' \
--data-urlencode 'dob%5Byear%5D=1970' \
--data-urlencode 'email=jdoe@email.com' \
--data-urlencode 'phone=+447400123456' \
--data-urlencode 'id_number=123456789' \
--data-urlencode 'relationship%5Bdirector%5D=true' \
--data-urlencode 'relationship%5Bexecutive%5D=true' \
--data-urlencode 'relationship%5Bowner%5D=true' \
--data-urlencode 'relationship%5Brepresentative%5D=true' \
--data-urlencode 'relationship%5Btitle%5D=CEO' \
--data-urlencode 'verification%5Bdocument%5D%5Bfront%5D=file_identity_document_success'
```

## Accept TOS and confirm persons

```
curl --location 'https://api.stripe.com/v1/accounts/{{ACCOUNT_ID}}' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Bearer sk_*****' \
--data-urlencode 'company%5Bowners_provided%5D=true' \
--data-urlencode 'company%5Bdirectors_provided%5D=true' \
--data-urlencode 'company%5Bexecutives_provided%5D=true' \
--data-urlencode 'company%5Bownership_declaration%5D%5Bip%5D=127.0.0.1' \
--data-urlencode 'company%5Bownership_declaration%5D%5Bdate%5D=1715193372' \
--data-urlencode 'external_account=btok_gb_gbp'
```

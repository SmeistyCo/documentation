# Smeisty API Reference

For authentication, send your **API_KEY** in headers of the request.

## Cold Storage Verification

API Url: `https://smeisty.app/api/wallets/coldVerifications`

### Add new wallet for verification

Method: `POST`
Body: `{ wallet: #WALLET_ADDRESS# }`

Example request

    curl --request POST \
      --url https://smeisty.app/api/wallets/coldVerifications \
      --header 'Content-Type: application/json' \
      --header 'apikey: #API_KEY#' \
      --data '{
      "wallet": "0x00f9A9e794488D40e32aA75499c99bF4182060F1"
    }'


### Get all verification requests

Method: `GET`

Example request

    curl --request GET \
      --url https://smeisty.app/api/wallets/coldVerifications \
      --header 'apikey: #API_KEY#'

Response Example:

    [
      {
        "id": "00663548-4114-492a-a614-4ca3479df62d",
        "wallet": "0x00f9a9e794488d40e32aa75499c99bf4182060f1",
        "verified": false,
        "amount": 0.00043608,
        "smeistyWallet": "0x51338e34fe4e0b80d85711bb5e373ab25aa301d8",
        "transactionHash": null,
        "developerId": "7bf7fcff-718b-4492-8634-e1f8b700b0ad"
      },
          .
          .
          .
      {
        "id": "02b22c92-d4c4-4417-ac5b-a64c5e590f74",
        "wallet": "0x00f9a9e794488d40e32aa75499c99bf4182060f1",
        "verified": false,
        "amount": 0.00064255,
        "smeistyWallet": "0x51338e34fe4e0b80d85711bb5e373ab25aa301d8",
        "transactionHash": null,
        "developerId": "7bf7fcff-718b-4492-8634-e1f8b700b0ad"
      }
    ]

### Get status of a verification request

To get the status for a single verification request.

Method: `GET`

Example request

    curl --request GET \
      --url https://smeisty.app/api/wallets/coldVerifications/00052079-045f-47a2-9891-b6ebd586778e \
      --header 'apikey: #API_KEY#'

### Delete a verification request

To delete a verification request

Method: `DELETE`

Example request

    curl --request GET \
      --url https://smeisty.app/api/wallets/coldVerifications \
      --header 'apikey: #API_KEY#'


# Gettext Cloud Translate

This little program will simplify starting a new Gettext translation
by letting you send the untranslated entries through Google Translate
via the GCP Cloud Translate.

## Installation

Run

    cargo install cloud-translate

## Usage

To use the script, you need a Google Cloud account. Install `gcloud`
and setup [application default credentials][1].

[1]: https://cloud.google.com/docs/authentication/application-default-credentials#personal

You do that by running

    gcloud auth application-default login

When that is done, you should be able to see an access token by
running

    gcloud auth application-default print-access-token

You will need to create a new Google Cloud project. The project ID is
needed for running `cloud-translate`:

    cargo run -- your-project-id-123456 some-path/xx.po 10000

The `10000` argument denotes the number of Unicode characters you want
to translate: Cloud Translate is priced per character you translate.
Currently, you get [500k characters for free per month][2].

[2]: https://cloud.google.com/translate/pricing

## License

Licensed under the [Apache-2.0 license][3].

[3]: https://github.com/mgeisler/cloud-translate/blob/main/LICENSE

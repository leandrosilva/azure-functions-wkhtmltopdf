# azure-functions-wkhtmltopdf

This is a simple image adding the latest **wkhtmltopdf** to a **microsoft/azure-functions-node8**, which currently is a **stretch**. The sole purpose of this image is to pack a wkhtmltopdf to go with my apps to Azure Functions.

    docker run -v $PWD:/pdf_files --name azure_wk leandr0silva/azure-functions-wkhtmltopdf

Or build it yourself:

    git clone https://github.com/leandrosilva/azure-functions-wkhtmltopdf.git
    cd azure-functions-wkhtmltopdf
    docker build -f Dockerfile -t azure-functions-wkhtmltopdf .
    docker run -v $PWD:/pdf_files --name azure_wk azure-functions-wkhtmltopdf

And then test it:

    docker exec azure_wk wkhtmltopdf http://google.com /pdf_files/google_home.pdf
    docker exec azure_wk ls -la /pdf_files

Enjoy!

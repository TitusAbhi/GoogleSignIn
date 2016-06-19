# GoogleSignIn

Note: Need to server client id in Strings.xml file. 

App is sign with google account and auth code. 

Reference: https://developers.google.com/identity/sign-in/android/start-integrating

Google APIs need access token inorder to consume the API , for example Contact API.

Auth code we got from this sample can be used to get Access token simply by Http request
 Ex:  httpClient = new DefaultHttpClient();
            httpPost = new HttpPost(address);
            params.add(new BasicNameValuePair("code", authCode));
            params.add(new BasicNameValuePair("client_id", client_id));
            params.add(new BasicNameValuePair("redirect_uri", redirect_uri));
            params.add(new BasicNameValuePair("grant_type", grant_type));
            httpPost.setHeader("Content-Type", "application/x-www-form-urlencoded");
            httpPost.setEntity(new UrlEncodedFormEntity(params));
            HttpResponse httpResponse = httpClient.execute(httpPost);
            HttpEntity httpEntity = httpResponse.getEntity();
            is = httpEntity.getContent();
  
 Once we received the Access Token , we can call any authorized API

# Test Driven Development of an API

## How to write tests for Django rest framework

The structure of a test.

class GetAllRecords(APITestCase):
    def setUp(self):


When testing just the functionality of views, you can use APIRequestFactory
Test the views first followed by the end-to-end testcase. 

generic views already contain GET, POST, etc.


        
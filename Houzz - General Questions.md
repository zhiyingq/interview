# Houzz - General Questions
#面试相关

1.Why HOUZZ?
I attended the HOUZZ information session last month, which impressed a lot. At first, I just know that HOUZZ is a company which provides interior design and decorating. But from the info session, I saw the pictures of your work place, which is bright, relaxed, friendly and has a modern design. What impressed me most is that, HOUZZ got the “Best App” at Google’s Play Awards and the number of software engineers at HOUZZ is about 200. So this is quite incredible and makes me believe working in HOUZZ will be meaningful and I will learn a lot of things. So this is attractive to me. 

2.Introduce yourself.
My name is Zhiying Qian, and I am a Computer Science master student at UC Irvine. I have some experience in both front-end and back-end development. And I have some independent projects, for example, I implemented a ticket recommendation website, which can load the nearby ticket information for users, and make personalized recommendation based on history data. I have a quick learning ability and I love learning new things. For example, I am now studying React and developing another full-stack website based on it. I really hope to get the internship opportunity at HOUZZ because I think I can learn a lot of technologies here. And I really like the working environment at HOUZZ.	

4.HKUST – DNN
I worked as a research assistant at Hong Kong University of Science and Techonology. At that time, logistics company many receive many malicious claims. For example, some customers may destroy or cheat that they have never received the product. Then the logistics company may have to pay a claim. So we create a DNN model, with the features of customers and the product as parameters, we hope to predict whether the customers will make a malicious claim. 

5.What happens when you type an URL in the browser and press enter?
1.the browser will check the cache for a DNS record to find the corresponding IP address.
2.If not found, go to the DNS server to get the IP
3.the browser will initiate a TCP connection with the server (TCP/IP three-way handshake)
	1. Client machine sends a SYN packet to the server over the internet asking if it is open for new connections.
	2. If the server has open ports that can accept and initiate new connections, it’ll respond with an ACKnowledgment of the SYN packet using a SYN/ACK packet.
	3. The client will receive the SYN/ACK packet from the server and will acknowledge it by sending an ACK packet.
4.* the browser sends an HTTP request to the web server
5.* the server handles the request and sends back a response
6.* the browser will display the HTML content
	

6. Ajax:
Procedure:
When an event occurs (eventListener), a XMLHttpReqeust object will be created and a request will be sent to the web server. The server will deal with the request and send back the response and data. The front page browser will deal with the data using javascript and show the updated page content.


7. HTML post and get request:
GET requests data from the web server. 
	-* Note that the query string (name/value pairs) is sent in the **URL of a GET request**

POST **sends data to the web server to create/update a resource**. The data is included in the body of the request.

8. HTML: DOM Tree
<html>: represents the root of an HTML documents, all other elements must be descendants of this element.

9. Gcd， new ton’s method
```
private int GCD(int a, int b) {
     if(b==0) return a; 
	   return a % b == 0 ? b : GCD(b, a % b);
}

public int mySqrt(int x) {
      int temp = x;
		while (temp != 0 && x / temp < temp) {
			temp = x / temp +  (temp - x / temp) / 2;    
		}
		return temp;
	}

f(x_n+1) = xn - f(xn)/f'(xn)
```

10. LocalStorage, SessionStorage, Cookie
LocalStorage
Stores data with **no expiration date**, and **gets cleared only through JavaScript, or clearing the Browser cache / Locally Stored Data**
Storage limit is the maximum amongst the three

SessionStorage
The sessionStorage object stores data **only for a session**, meaning that the data is stored **until the browser (or tab) is closed.**
Data is never transferred to the server.
Storage limit is larger than a cookie (at least 5MB).

Cookie
Stores data that **has to be sent back to the server with subsequent requests**. Its expiration varies based on the type and the expiration duration can be set from either server-side or client-side (normally from server-side).
Cookies are primarily for server-side reading (can also be read on client-side), localStorage and sessionStorage can only be read on client-side.
Size must be less than 4KB.
Cookies can be made secure by setting the httpOnly flag as true for that cookie. This prevents client-side access to that cookie

11. Next palindrome
```
private long getLarger(long num) {
        char[] digits = String.valueOf(num).toCharArray();
        int n = digits.length;
        char[] copy = Arrays.copyOf(digits, n);
        copyLeftToRight(copy);
        for (int i = 0; i < n; i++) {
            if (digits[i] < copy[i]) { return Long.parseLong(String.valueOf(copy)); }
            else if (digits[i] > copy[i]) {
                for (int j = (n - 1) / 2; j >= 0; j--) {
                    if (++copy[j] > '9') {
                        copy[j] = '0';
                    } else {
                        break;
                    }
                }
                copyLeftToRight(copy);
                return Long.parseLong(String.valueOf(copy));
            }
        }
        return Long.parseLong(String.valueOf(copy));  
    }
    
    public Long getSmaller(Long limit) {
        String n = Long.toString(limit);
        char[] s = n.toCharArray();
        int m = s.length;
        char[] t = Arrays.copyOf(s, m);
        for (int i = 0; i < m / 2; i++) {
            t[m - 1 - i] = t[i];
        }
        for (int i = 0; i < m; i++) {
            if (s[i] > t[i]) {
                return Long.parseLong(String.valueOf(t)); 
            } else if (s[i] < t[i]) {
                for (int j = (m - 1) / 2; j >= 0; j--) {
                    if (--t[j] < '0') {
                        t[j] = '9';
                    } else {
                        break;
                    }
                }
                if (t[0] == '0') {
                    char[] a = new char[m - 1];
                    Arrays.fill(a, '9');
                    return Long.parseLong(String.valueOf(a)); 
                }
                // make it palindrome again
                for (int k = 0; k < m / 2; k++) {
                    t[m - 1 - k] = t[k];
                }
                return Long.parseLong(String.valueOf(t)); 
            }
        }
         return Long.parseLong(String.valueOf(t));  
    }
```


12. What is deadlock?
A lock occurs when multiple processes try to access the same resource at the same time.
One process loses out and must wait for the other to finish.
A deadlock occurs when the waiting process is still holding on to another resource that the first needs before it can finish.

So, an example:

Resource A and resource B are used by process X and process Y

X starts to use A.
X and Y try to start using B
Y 'wins' and gets B first
now Y needs to use A
A is locked by X, which is waiting for Y
The best way to avoid deadlocks is to avoid having processes cross over in this way. Reduce the need to lock anything as much as you can.

In databases avoid making lots of changes to different tables in a single transaction, avoid triggers and switch to optimistic_dirty_nolock reads as much as possible.









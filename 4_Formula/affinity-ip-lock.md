You are asking about the technical process behind YouTube's A/B testing, specifically how it ensures a user consistently sees the *same* thumbnail during a test.

While your premise of "locking to an IP" is on the right track conceptually—it's about ensuring consistency—YouTube almost certainly **does not use your IP address** for this.

A simple IP lock is an unreliable method. Your IP can change (e.g., moving from Wi-Fi to cellular) or be shared by many people (like at a university or office).

Instead, YouTube's system uses more persistent and reliable identifiers to achieve "user affinity" or a "sticky session." Here is a breakdown of the process.

***

### 1. What is YouTube's Thumbnail A/B Test?

This feature, officially called **"Test & Compare,"** allows a creator to upload two or three different thumbnails for a single video.

* **Splitting the Audience:** For a set period (from a few hours to two weeks), YouTube randomly splits the video's viewers into groups.
* **Group A** sees Thumbnail A.
* **Group B** sees Thumbnail B.
* **Group C** sees Thumbnail C (if one is added).
* **Finding the Winner:** YouTube doesn't just measure the **click-through rate (CTR)**. Its main goal is to promote videos that keep people on the platform. Therefore, the winning thumbnail is the one that leads to the highest **"watch time share."**
* **Declaring a Winner:** Once the test has enough data to be statistically confident, YouTube anoints a "Winner" or "Preferred" thumbnail and automatically shows it to all future viewers.

### 2. The Need for "Affinity" (The "Lock")

For the test to be accurate, it's critical that a single viewer doesn't get confused. This is the "affinity" you're asking about.

Imagine this bad experience:
1.  You see Thumbnail A on your homepage and are interested.
2.  You don't click immediately.
3.  An hour later, you refresh your homepage and now see the *same video* with Thumbnail B.

This is confusing for the user and contaminates the test data. The user's "vote" (their click or non-click) is now muddled. To prevent this, YouTube must ensure that **once you are assigned to Group A, you *always* see Thumbnail A** for that video, no matter where you see it on the platform (homepage, subscription feed, search, etc.).

### 3. How YouTube *Actually* "Locks" the Thumbnail

YouTube achieves this "lock" by assigning you to a test bucket using a stable identifier, not your IP. The method depends on whether you are logged in.

#### **Case 1: You Are Logged In (The Easiest Way)**

This is simple. The system "locks" the test version to your **YouTube/Google Account ID**.

* When the test starts, your account ID (e.g., `User_12345`) is randomly assigned to a group (e.g., "Group B").
* This decision (`User_12345` = `Group B` for `Video_XYZ`) is saved on YouTube's servers.
* It doesn't matter if you log in from your phone, your laptop, or your smart TV. As long as you are logged in as `User_12345`, you will *always* see Thumbnail B for that video until the test concludes.



#### **Case 2: You Are Logged Out (The More Common Way)**

This is more complex and where the "sticky session" concept comes in. Since YouTube doesn't know your account ID, it uses identifiers tied to your browser or device.

* **Browser Cookies:** The most likely method. When you first load YouTube, the A/B testing system is triggered. It assigns your browser session to a group (e.g., "Group A") and stores this information in a cookie (a small text file) in your browser.
* **The "Lock":** Now, every time you interact with YouTube, its servers read that cookie. When it's time to show you the thumbnail for `Video_XYZ`, the server sees your cookie, looks up your assignment, and serves you Thumbnail A.
* **Device Identifiers:** On mobile apps, a similar logic applies using your phone's unique "advertising identifier" or another anonymous device ID.

This is why clearing your cookies or using an incognito window might suddenly show you a different thumbnail—you've just erased the "lock" and have been assigned to a new test group as a "new" user.

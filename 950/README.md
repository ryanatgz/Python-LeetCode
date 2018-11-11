# LeegtCode 901-950

929 [Unique Email Addresses](https://leetcode.com/problems/unique-email-addresses)
```python
class Solution(object):
    def numUniqueEmails(self, emails):
        """
        :type emails: List[str]
        :rtype: int
        """
        ret = {self.simplifyEmail(email): True for email in emails}
        return len(ret.keys())

    def simplifyEmail(self, email):
        name, domain = email.split('@')
        return ''.join(name.split('+')[0].split('.')) + '@' + domain
```
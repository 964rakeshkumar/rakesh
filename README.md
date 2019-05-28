# rakesh
Two character problem of hackerrank
start---
bool valid(string ss) {
  for (int i = 0; i < ss.length(); i++) {
    if (ss[i] == ss[i + 1])
      return false;
  }
  return true;
}
int alternate(string s) {
    if(s.length()==1)
    return 0;
  std::set<char> s1;
  int n = s.length();
  for (int i = 0; i < n; i++)
    s1.insert(s[i]);
  string str = " ";
  int maxlen = 0;
  set<char>::iterator it;
  for (it = s1.begin(); it != s1.end(); it++) {
    str = str + *it;
  }
  int l = str.length();
  for (int i = 0; i < l - 1; i++) {
    char x = str[i];
    for (int j = i + 1; j < l; j++) {
      char y = str[j];
      string res = " ";
      for (int k = 0; k < n; k++) {
        if (s[k] == x || s[k] == y) {
          res = res + s[k];
        }
      }
      if (valid(res) == true) {
        if (maxlen < res.length())
          maxlen = res.length();
      }
    }
  }
  if(maxlen==0)
  return 0;
  else
  return maxlen-1;
}

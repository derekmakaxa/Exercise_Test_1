#A. match_ends
def match_ends(words):
  number = 0

  for character in words:
    if len(character) > 1 and character[0] == character[-2]:
      number += 1

  return number
strs = ['cccd']

match_ends(strs)

def match_ends(words):
  number = 0

  for character in words:
    if len(character) > 1 and character[0] == character[-2]:
      number += 1

  return number
strs = ['cccc']

match_ends(strs)

#B. front_x
def front_x(words):
  list_a = []
  list_x = []

  for word in words:
    if word.startswith('x'):
      list_x.append(word)
    else:
      list_a.append(word)

  return sorted(list_x) + sorted(list_a)
strs = ['mix', 'xyz', 'apple', 'xanadu', 'aardvark'] 
front_x(strs)
#C. sort_last

def last(t): return t[-1]

def sort_last(tuples):
  return sorted(tuples, key=last)

def test(got, expected):
  if got == expected:
    prefix = ' OK '
  else:
    prefix = '  X '
  print ' {} got: {!r} expected: {!r}'.format(prefix, got, expected)
  
def main():
  print 'match_ends'
  test(match_ends(['aba', 'xyz', 'aa', 'x', 'bbb']), 3)
  test(match_ends(['', 'x', 'xy', 'xyx', 'xx']), 2)
  test(match_ends(['aaa', 'be', 'abc', 'hello']), 1)

  print
  print 'front_x'
  test(front_x(['bbb', 'ccc', 'axx', 'xzz', 'xaa']),
       ['xaa', 'xzz', 'axx', 'bbb', 'ccc'])
  test(front_x(['ccc', 'bbb', 'aaa', 'xcc', 'xaa']),
       ['xaa', 'xcc', 'aaa', 'bbb', 'ccc'])
  test(front_x(['mix', 'xyz', 'apple', 'xanadu', 'aardvark']),
       ['xanadu', 'xyz', 'aardvark', 'apple', 'mix'])


  print
  print 'sort_last'
  test(sort_last([(1, 3), (3, 2), (2, 1)]),
       [(2, 1), (3, 2), (1, 3)])
  test(sort_last([(2, 3), (1, 2), (3, 1)]),
       [(3, 1), (1, 2), (2, 3)])
  test(sort_last([(1, 7), (1, 3), (3, 4, 5), (2, 2)]),
       [(2, 2), (1, 3), (3, 4, 5), (1, 7)])

#D. remove_adjacent
if __name__ == '__main__':
  main()

def remove_adjacent(nums):
  list = []

  for number in nums:
    if not(number in list):
      list.append(number)

  return list
str = [1,2,2,3]
remove_adjacent(str)
#E. linear_merge

def linear_merge(list_1, list_2):
      list_1.extend(list_2) 
      return sorted(list_1)
str1 = ['aa']
str2 = ['bb']
linear_merge(str1,str2)
def main():
    print 'remove_adjacent'
    test(remove_adjacent([1, 2, 2, 3]), [1, 2, 3])
    test(remove_adjacent([2, 2, 3, 3, 3]), [2, 3])
    test(remove_adjacent([]), [])

    print
    print 'linear_merge'
    test(linear_merge(['aa', 'xx', 'zz'], ['bb', 'cc']),
        ['aa', 'bb', 'cc', 'xx', 'zz'])
    test(linear_merge(['aa', 'xx'], ['bb', 'cc', 'zz']),
        ['aa', 'bb', 'cc', 'xx', 'zz'])
    test(linear_merge(['aa', 'aa'], ['aa', 'bb', 'bb']),
        ['aa', 'aa', 'aa', 'bb', 'bb'])
#A. donuts
def donuts(count):
  if count > 9:
    number = 'many'
  else:
    number = str(count)
  return number
#B both end
def both_ends(s):
  if len(s) < 2:
    return ''

  return s[0:2] + s[-2:]
#C fix start
def fix_start(s):
  char = s[0]
  s = s.replace(char, '*')
  s = char + s[1:]
#D mix up
def mix_up(a, b):
  mix_a = b[:2] + a[2:]
  mix_b = a[:2] + b[2:]


  return mix_a + ' ' + mix_b

  return s
def main():
    print 'donuts'
    # Each line calls donuts, compares its result to the expected for that call.
    test(donuts(4), '4')
    test(donuts(9), '9')
    test(donuts(10), 'many')
    test(donuts(99), 'many')

    print
    print 'both_ends'
    test(both_ends('spring'), 'spng')
    test(both_ends('Hello'), 'Helo')
    test(both_ends('a'), '')
    test(both_ends('xyz'), 'xyyz')

  
    print
    print 'fix_start'
    test(fix_start('babble'), 'ba**le')
    test(fix_start('aardvark'), 'a*rdv*rk')
    test(fix_start('google'), 'goo*le')
    test(fix_start('donut'), 'donut')

    print
    print 'mix_up'
    test(mix_up('mix', 'pod'), 'pox mid')
    test(mix_up('dog', 'dinner'), 'dig donner')
    test(mix_up('gnash', 'sport'), 'spash gnort')
    test(mix_up('pezzy', 'firm'), 'fizzy perm')
 #D verbing
 def verbing(s):
    if s[-3:] == 'ing':
        return s
    else:
 #E Not bad
 def not_bad(s):
  string_not = s.find('not')
  string_bad = s.find('bad')

  if string_bad > string_not:
    s = s.replace(s[string_not:(string_bad+3)], 'good')

  return s
#F Front Back
def front_back(a, b):
  length_a = len(a)
  length_b = len(b)

  if length_a % 2 == 0:
    index_a = length_a // 2
  else:
    index_a = (length_a // 2) + 1

  if length_b % 2 == 0:
    index_b = length_b // 2
  else:
    index_b = (length_b // 2) + 1

  front_a = a[0:index_a]
  back_a = a[index_a:]

  front_b = b[0:index_b]
  back_b = b[index_b:]

  return front_a + front_b + back_a + back_b
def main():
    print 'verbing'
    test(verbing('hail'), 'hailing')
    test(verbing('swiming'), 'swimingly')
    test(verbing('do'), 'do')
    
    print
    print 'not_bad'
    test(not_bad('This movie is not so bad'), 'This movie is good')
    test(not_bad('This dinner is not that bad!'), 'This dinner is good!')
    test(not_bad('This tea is not hot'), 'This tea is not hot')
    test(not_bad("It's bad yet not"), "It's bad yet not")

    print
    print 'front_back'
    test(front_back('abcd', 'xy'), 'abxcdy')
    test(front_back('abcde', 'xyz'), 'abcxydez')
    test(front_back('Kitten', 'Donut'), 'KitDontenut')
        return s + 'ing'

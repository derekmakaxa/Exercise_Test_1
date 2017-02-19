Exercise 1
def match_ends(words):
  number = 0

  for character in words:
    if len(character) > 1 and character[0] == character[-2]:
      number += 1

  return number
strs = ['cccd']

match_ends(strs)
# the return result will be 0 
def match_ends(words):
  number = 0

  for character in words:
    if len(character) > 1 and character[0] == character[-2]:
      number += 1

  return number
strs = ['cccc']

match_ends(strs)
# the return result will be 0 

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
# the return will be ['xanadu', 'xyz', 'aardvark', 'apple', 'mix']

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


if __name__ == '__main__':
  main()
#Section D
def remove_adjacent(nums):
  list = []

  for number in nums:
    if not(number in list):
      list.append(number)

  return list
str = [1,2,2,3]
remove_adjacent(str)
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
      

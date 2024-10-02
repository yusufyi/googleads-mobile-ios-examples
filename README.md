Bu liste, **DOM Testing Library** için çeşitli sorgu fonksiyonlarını ve bunların nasıl kullanıldığını özetlemektedir. Aşağıda, bu sorgu fonksiyonlarının Türkçe açıklamalarını ve kullanımlarını özetledim:

### Sorgu Fonksiyonları

| Fonksiyon           | Hiç Eşleşme Yok | Tek Eşleşme | Birden Fazla Eşleşme | Beklenir mi? (Await) |
|---------------------|-----------------|-------------|----------------------|----------------------|
| **getBy**           | Hata atar       | Döner       | Hata atar            | Hayır                |
| **findBy**          | Hata atar       | Döner       | Hata atar            | Evet                 |
| **queryBy**         | `null` döner    | Döner       | Hata atar            | Hayır                |
| **getAllBy**        | Hata atar       | Dizi döner  | Dizi döner           | Hayır                |
| **findAllBy**       | Hata atar       | Dizi döner  | Dizi döner           | Evet                 |
| **queryAllBy**      | Boş dizi döner  | Dizi döner  | Dizi döner           | Hayır                |

### `ByLabelText` Fonksiyonları (Label ya da `aria-label` ile eleman bulma)
- **getByLabelText**: Bir `label` ya da `aria-label` içeriğine göre eleman bulur. Bulamazsa hata atar.
- **queryByLabelText**: Eleman bulursa döner, bulamazsa `null` döner.
- **getAllByLabelText**: Birden fazla eleman bulursa dizi döner, bulamazsa hata atar.
- **queryAllByLabelText**: Birden fazla eleman bulursa dizi döner, bulamazsa boş dizi döner.
- **findByLabelText**: Asenkron olarak eleman bulur, Promise döner.
- **findAllByLabelText**: Birden fazla elemanı asenkron bulur, Promise döner.

### `ByPlaceholderText` Fonksiyonları (Placeholder ile eleman bulma)
- **getByPlaceholderText**: Placeholder değerine göre eleman bulur, bulamazsa hata atar.
- **queryByPlaceholderText**: Eleman bulursa döner, bulamazsa `null` döner.
- **getAllByPlaceholderText**: Birden fazla eleman bulursa dizi döner, bulamazsa hata atar.
- **queryAllByPlaceholderText**: Birden fazla eleman bulursa dizi döner, bulamazsa boş dizi döner.
- **findByPlaceholderText**: Asenkron olarak eleman bulur, Promise döner.
- **findAllByPlaceholderText**: Birden fazla elemanı asenkron bulur, Promise döner.

### `ByText` Fonksiyonları (Metin içeriğine göre eleman bulma)
- **getByText**: Metin içeriğine göre eleman bulur, bulamazsa hata atar.
- **queryByText**: Eleman bulursa döner, bulamazsa `null` döner.
- **getAllByText**: Birden fazla eleman bulursa dizi döner, bulamazsa hata atar.
- **queryAllByText**: Birden fazla eleman bulursa dizi döner, bulamazsa boş dizi döner.
- **findByText**: Asenkron olarak eleman bulur, Promise döner.
- **findAllByText**: Birden fazla elemanı asenkron bulur, Promise döner.

### `ByDisplayValue` Fonksiyonları (Form elementinin geçerli değerine göre eleman bulma)
- **getByDisplayValue**: Form elementinin mevcut değerine göre eleman bulur, bulamazsa hata atar.
- **queryByDisplayValue**: Eleman bulursa döner, bulamazsa `null` döner.
- **getAllByDisplayValue**: Birden fazla eleman bulursa dizi döner, bulamazsa hata atar.
- **queryAllByDisplayValue**: Birden fazla eleman bulursa dizi döner, bulamazsa boş dizi döner.
- **findByDisplayValue**: Asenkron olarak eleman bulur, Promise döner.
- **findAllByDisplayValue**: Birden fazla elemanı asenkron bulur, Promise döner.

### `ByAltText` Fonksiyonları (Görselin `alt` attribute değerine göre eleman bulma)
- **getByAltText**: `alt` attribute değerine göre eleman bulur, bulamazsa hata atar.
- **queryByAltText**: Eleman bulursa döner, bulamazsa `null` döner.
- **getAllByAltText**: Birden fazla eleman bulursa dizi döner, bulamazsa hata atar.
- **queryAllByAltText**: Birden fazla eleman bulursa dizi döner, bulamazsa boş dizi döner.
- **findByAltText**: Asenkron olarak eleman bulur, Promise döner.
- **findAllByAltText**: Birden fazla elemanı asenkron bulur, Promise döner.

### `ByRole` Fonksiyonları (Aria rolüne göre eleman bulma)
- **getByRole**: Aria rolüne göre eleman bulur, bulamazsa hata atar.
- **queryByRole**: Eleman bulursa döner, bulamazsa `null` döner.
- **getAllByRole**: Birden fazla eleman bulursa dizi döner, bulamazsa hata atar.
- **queryAllByRole**: Birden fazla eleman bulursa dizi döner, bulamazsa boş dizi döner.
- **findByRole**: Asenkron olarak eleman bulur, Promise döner.
- **findAllByRole**: Birden fazla elemanı asenkron bulur, Promise döner.

### `ByTestId` Fonksiyonları (Veri Test ID'sine göre eleman bulma)
- **getByTestId**: `data-testid` attribute'u ile eleman bulur, bulamazsa hata atar.
- **queryByTestId**: Eleman bulursa döner, bulamazsa `null` döner.
- **getAllByTestId**: Birden fazla eleman bulursa dizi döner, bulamazsa hata atar.
- **queryAllByTestId**: Birden fazla eleman bulursa dizi döner, bulamazsa boş dizi döner.
- **findByTestId**: Asenkron olarak eleman bulur, Promise döner.
- **findAllByTestId**: Birden fazla elemanı asenkron bulur, Promise döner.

Tabii! Aşağıda DOM Testing Library'de kullanılan tüm sorgu fonksiyonları için küçük örnekler yazdım:

### 1. **`getBy` Örnekleri**
- Tek bir eleman bulduğunda, döner; bulamazsa hata atar.

```javascript
const { getByText } = render(<div>Hello World</div>);
const element = getByText('Hello World'); // Elemanı bulur
```

### 2. **`findBy` Örnekleri**
- Asenkron çalışır ve Promise döner. Eleman bulamazsa hata atar.

```javascript
const { findByText } = render(<div>Hello World</div>);
const element = await findByText('Hello World'); // Promise döner, elemanı bulur
```

### 3. **`queryBy` Örnekleri**
- Eleman bulursa döner, bulamazsa `null` döner.

```javascript
const { queryByText } = render(<div>Hello World</div>);
const element = queryByText('Hello Universe'); // null döner, çünkü eleman yok
```

### 4. **`getAllBy` Örnekleri**
- Birden fazla eleman bulursa dizi döner, bulamazsa hata atar.

```javascript
const { getAllByText } = render(
  <>
    <div>Hello</div>
    <div>Hello</div>
  </>
);
const elements = getAllByText('Hello'); // ["<div>Hello</div>", "<div>Hello</div>"]
```

### 5. **`findAllBy` Örnekleri**
- Asenkron çalışır ve Promise döner. Birden fazla eleman bulur, bulamazsa hata atar.

```javascript
const { findAllByText } = render(
  <>
    <div>Hello</div>
    <div>Hello</div>
  </>
);
const elements = await findAllByText('Hello'); // Promise döner ve tüm elemanları bulur
```

### 6. **`queryAllBy` Örnekleri**
- Birden fazla eleman bulursa dizi döner, bulamazsa boş dizi döner.

```javascript
const { queryAllByText } = render(<div>Hello Universe</div>);
const elements = queryAllByText('Hello'); // Boş dizi döner []
```

---

### 7. **`ByLabelText` Örnekleri**
- Eleman `label` ya da `aria-label` ile bulunur.

```javascript
const { getByLabelText } = render(
  <>
    <label htmlFor="username">Username</label>
    <input id="username" />
  </>
);
const input = getByLabelText('Username'); // input elemanını bulur
```

### 8. **`ByPlaceholderText` Örnekleri**
- Eleman placeholder değeri ile bulunur.

```javascript
const { getByPlaceholderText } = render(<input placeholder="Enter name" />);
const input = getByPlaceholderText('Enter name'); // input elemanını bulur
```

### 9. **`ByText` Örnekleri**
- Metin içeriği ile eleman bulunur.

```javascript
const { getByText } = render(<div>Click Me</div>);
const button = getByText('Click Me'); // butonu bulur
```

### 10. **`ByDisplayValue` Örnekleri**
- Form elementinin mevcut değeri ile eleman bulunur.

```javascript
const { getByDisplayValue } = render(<input value="John" />);
const input = getByDisplayValue('John'); // input elemanını bulur
```

### 11. **`ByAltText` Örnekleri**
- Görselin `alt` attribute değeri ile eleman bulunur.

```javascript
const { getByAltText } = render(<img alt="Profile picture" src="/profile.jpg" />);
const img = getByAltText('Profile picture'); // Görseli bulur
```

### 12. **`ByTitle` Örnekleri**
- `title` attribute veya `svg title` tag'ine göre eleman bulunur.

```javascript
const { getByTitle } = render(<div title="Close">X</div>);
const closeButton = getByTitle('Close'); // Butonu bulur
```

### 13. **`ByRole` Örnekleri**
- Aria rolüne göre eleman bulunur.

```javascript
const { getByRole } = render(<button role="button">Submit</button>);
const button = getByRole('button'); // Butonu bulur
```

### 14. **`ByTestId` Örnekleri**
- `data-testid` attribute ile eleman bulunur.

```javascript
const { getByTestId } = render(<div data-testid="custom-element">Content</div>);
const element = getByTestId('custom-element'); // Elemanı bulur
```

---

### **Async İşlemler ve Event Testi**

#### Async İşlem Örneği:

```javascript
test('async element loading', async () => {
  const { findByText } = render(<ComponentWithAsyncAction />);
  const element = await findByText('Loaded Element');
  expect(element).toBeInTheDocument(); // Eleman bulundu
});
```

#### `fireEvent` Kullanımı:

```javascript
const { getByText } = render(<button onClick={() => alert('Clicked!')}>Click Me</button>);
fireEvent.click(getByText('Click Me')); // Tıklama olayını tetikler
```

`expect` ifadesi, Jest testlerinde bir değeri ya da sonucu kontrol etmek için kullanılır. DOM Testing Library ile birlikte `expect`, belirli bir DOM elemanının var olup olmadığını, doğru özelliklere sahip olup olmadığını ya da doğru şekilde render edilip edilmediğini test etmek için kullanılır.

Aşağıda çeşitli sorgu fonksiyonlarıyla birlikte nasıl `expect` kullanılacağını gösteren örnekler var:

### 1. **`getBy` ile `expect` Kullanımı**
```javascript
const { getByText } = render(<div>Hello World</div>);
const element = getByText('Hello World');
expect(element).toBeInTheDocument();  // Elemanın DOM içinde var olduğunu doğrular
```

### 2. **`findBy` ile `expect` Kullanımı**
```javascript
const { findByText } = render(<div>Hello World</div>);
const element = await findByText('Hello World');
expect(element).toBeInTheDocument();  // Asenkron olarak elemanın DOM'da olup olmadığını kontrol eder
```

### 3. **`queryBy` ile `expect` Kullanımı**
```javascript
const { queryByText } = render(<div>Hello Universe</div>);
const element = queryByText('Hello World');
expect(element).toBeNull();  // Eleman bulunmazsa `null` döner ve bunu doğrular
```

### 4. **`getAllBy` ile `expect` Kullanımı**
```javascript
const { getAllByText } = render(
  <>
    <div>Hello</div>
    <div>Hello</div>
  </>
);
const elements = getAllByText('Hello');
expect(elements.length).toBe(2);  // İki eleman bulunduğunu doğrular
```

### 5. **`findAllBy` ile `expect` Kullanımı**
```javascript
const { findAllByText } = render(
  <>
    <div>Hello</div>
    <div>Hello</div>
  </>
);
const elements = await findAllByText('Hello');
expect(elements.length).toBe(2);  // Promise dönen iki elemanın varlığını doğrular
```

### 6. **`queryAllBy` ile `expect` Kullanımı**
```javascript
const { queryAllByText } = render(<div>Hello Universe</div>);
const elements = queryAllByText('Hello');
expect(elements.length).toBe(0);  // Hiç eleman bulunmadığını doğrular
```

---

### 7. **`ByLabelText` ile `expect` Kullanımı**
```javascript
const { getByLabelText } = render(
  <>
    <label htmlFor="username">Username</label>
    <input id="username" />
  </>
);
const input = getByLabelText('Username');
expect(input).toHaveAttribute('id', 'username');  // Elemanın id özelliğini doğrular
```

### 8. **`ByPlaceholderText` ile `expect` Kullanımı**
```javascript
const { getByPlaceholderText } = render(<input placeholder="Enter name" />);
const input = getByPlaceholderText('Enter name');
expect(input).toBeInTheDocument();  // Placeholder textine göre elemanın varlığını doğrular
```

### 9. **`ByText` ile `expect` Kullanımı**
```javascript
const { getByText } = render(<div>Click Me</div>);
const element = getByText('Click Me');
expect(element).toBeInTheDocument();  // Elemanın DOM'da olduğunu doğrular
```

### 10. **`ByDisplayValue` ile `expect` Kullanımı**
```javascript
const { getByDisplayValue } = render(<input value="John" />);
const input = getByDisplayValue('John');
expect(input).toHaveValue('John');  // Form elemanının mevcut değerini doğrular
```

### 11. **`ByAltText` ile `expect` Kullanımı**
```javascript
const { getByAltText } = render(<img alt="Profile picture" src="/profile.jpg" />);
const img = getByAltText('Profile picture');
expect(img).toHaveAttribute('src', '/profile.jpg');  // Görselin src özelliğini doğrular
```

### 12. **`ByTitle` ile `expect` Kullanımı**
```javascript
const { getByTitle } = render(<div title="Close">X</div>);
const button = getByTitle('Close');
expect(button).toBeInTheDocument();  // Title özelliğine göre elemanın varlığını doğrular
```

### 13. **`ByRole` ile `expect` Kullanımı**
```javascript
const { getByRole } = render(<button role="button">Submit</button>);
const button = getByRole('button');
expect(button).toBeInTheDocument();  // Aria rolüne göre butonun varlığını doğrular
```

### 14. **`ByTestId` ile `expect` Kullanımı**
```javascript
const { getByTestId } = render(<div data-testid="custom-element">Content</div>);
const element = getByTestId('custom-element');
expect(element).toHaveTextContent('Content');  // Elemanın içerdiği metni doğrular
```

---

### **Async İşlemlerle `expect` Kullanımı**

#### Async Eleman Testi:
```javascript
test('loads async content', async () => {
  const { findByText } = render(<AsyncComponent />);
  const element = await findByText('Loaded Content');
  expect(element).toBeInTheDocument();  // Elemanın yüklenmesini bekler ve DOM'da olduğunu doğrular
});
```

#### `fireEvent` ile Etkileşim Testi:
```javascript
const { getByText } = render(<button onClick={() => alert('Clicked!')}>Click Me</button>);
const button = getByText('Click Me');
fireEvent.click(button);  // Butona tıklama olayını tetikler
expect(button).toBeInTheDocument();  // Buton hala DOM'da mı diye kontrol eder
```

### **Common `expect` Matcher'ları**

- **`toBeInTheDocument()`**: Elemanın DOM'da olup olmadığını kontrol eder.
- **`toHaveTextContent()`**: Elemanın belirli bir metni içerip içermediğini kontrol eder.
- **`toHaveAttribute()`**: Elemanın belirli bir attribute'a sahip olup olmadığını kontrol eder.
- **`toHaveValue()`**: Form elemanının geçerli değerini kontrol eder.
- **`toBeNull()`**: Elemanın `null` olup olmadığını doğrular.

React Hook'ları ve fonksiyonları test ederken de Jest ve React Testing Library kullanarak `expect` ile çeşitli doğrulamalar yapabiliriz. Hook'lar genellikle asenkron yapılar veya bileşenlerin yaşam döngüsünü yöneten işlevler içerdiğinden, onları test etmek için birkaç özel yaklaşıma ihtiyacımız olur. İşte React Hook'ları ve fonksiyonları test etmek için kullanabileceğin `expect` örnekleri:

### 1. **Custom Hook'ların Test Edilmesi**

React Hook'larını test etmek için `@testing-library/react-hooks` kütüphanesini kullanabiliriz. Hook'un değerlerini veya yan etkilerini kontrol etmek için `expect` kullanabiliriz.

#### Basit bir Custom Hook Örneği:
```javascript
import { renderHook, act } from '@testing-library/react-hooks';
import useCounter from './useCounter'; // varsayılan olarak basit bir hook

// Hook'un başlangıç durumunu kontrol et
test('should increment counter', () => {
  const { result } = renderHook(() => useCounter());
  
  expect(result.current.count).toBe(0); // Başlangıçta 'count' 0 olmalı
  
  // `act` ile durumu güncelle ve sonucu test et
  act(() => {
    result.current.increment();
  });

  expect(result.current.count).toBe(1); // Arttıktan sonra 'count' 1 olmalı
});
```

### 2. **`useState` Hook'larının Test Edilmesi**

`useState` hook'u, React bileşenlerindeki durumu yönetir. Bu hook'u test ederken, durumu güncellemek için `act` kullanarak durumu simüle edebiliriz.

#### `useState` ile Bir Durum Güncelleme Testi:
```javascript
function useToggle(initialValue = false) {
  const [value, setValue] = React.useState(initialValue);
  const toggle = () => setValue((prevValue) => !prevValue);
  return [value, toggle];
}

test('should toggle value', () => {
  const { result } = renderHook(() => useToggle());
  
  expect(result.current[0]).toBe(false); // İlk değer 'false' olmalı
  
  act(() => {
    result.current[1](); // toggle fonksiyonunu çalıştır
  });

  expect(result.current[0]).toBe(true); // Değer 'true' olmalı
});
```

### 3. **`useEffect` Hook'larının Test Edilmesi**

`useEffect` yan etkileri (API çağrıları, zamanlayıcılar gibi) yönetir. Bu hook'un nasıl çalıştığını test ederken, özellikle yan etkilerin tetiklendiği anları kontrol etmek için `jest.fn()` gibi mock fonksiyonlar kullanabiliriz.

#### `useEffect`'in Yan Etkisini Test Etme:
```javascript
import { render, screen } from '@testing-library/react';
import React, { useEffect } from 'react';

// Basit bir useEffect kullanımı
function MyComponent({ onFetchData }) {
  useEffect(() => {
    onFetchData(); // dışarıdan gelen bir API çağrısı gibi düşün
  }, [onFetchData]);

  return <div>Fetching Data</div>;
}

test('should call onFetchData once after rendering', () => {
  const mockFetchData = jest.fn();
  
  render(<MyComponent onFetchData={mockFetchData} />);

  expect(mockFetchData).toHaveBeenCalledTimes(1); // useEffect bir kez çalıştırıldı mı?
});
```

### 4. **`useContext` Hook'unun Test Edilmesi**

`useContext` genellikle React'teki global durumu yönetmek için kullanılır. Hook'un test edilmesi için, context sağlayıcıyı (provider) bileşen çevresinde sarmalayarak, değerlerin doğru olup olmadığını kontrol edebiliriz.

#### `useContext` ile Durum Yönetimi Testi:
```javascript
const MyContext = React.createContext();

function MyComponent() {
  const value = React.useContext(MyContext);
  return <div>{value}</div>;
}

test('should render with context value', () => {
  render(
    <MyContext.Provider value="Hello Context">
      <MyComponent />
    </MyContext.Provider>
  );

  expect(screen.getByText('Hello Context')).toBeInTheDocument(); // Context değeri doğru render edildi mi?
});
```

### 5. **Asenkron Fonksiyonların ve `useEffect` Hook'larının Test Edilmesi**

Eğer `useEffect` içinde bir API çağrısı yapıyorsanız veya asenkron işlemler kullanıyorsanız, bunu mock'layarak test etmek isteyebilirsiniz. Örneğin, `fetch` fonksiyonunu mock'layarak API'den gelen verilerin doğru işlendiğini test edebiliriz.

#### Asenkron Bir `useEffect` İçeren Fonksiyonun Test Edilmesi:
```javascript
function FetchComponent() {
  const [data, setData] = React.useState(null);

  useEffect(() => {
    async function fetchData() {
      const response = await fetch('/api/data');
      const result = await response.json();
      setData(result);
    }
    fetchData();
  }, []);

  if (!data) return <div>Loading...</div>;
  return <div>{data.message}</div>;
}

test('should fetch and display data', async () => {
  global.fetch = jest.fn(() =>
    Promise.resolve({
      json: () => Promise.resolve({ message: 'Hello World' })
    })
  );

  render(<FetchComponent />);

  expect(screen.getByText('Loading...')).toBeInTheDocument(); // İlk olarak 'Loading' görünmeli

  const message = await screen.findByText('Hello World'); // Verinin yüklenmesini bekle
  expect(message).toBeInTheDocument(); // Verinin DOM'da olduğunu doğrula
});
```

### 6. **Fonksiyonların Test Edilmesi**

Eğer bir bileşen içinde belirli bir fonksiyon varsa, bu fonksiyonun doğru şekilde çalıştığını test etmek için Jest'in mock fonksiyonları ve `expect` kullanabilirsin.

#### Basit Bir Fonksiyon Testi:
```javascript
function sum(a, b) {
  return a + b;
}

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3); // Fonksiyonun doğru sonuç döndüğünü kontrol et
});
```

### 7. **Fonksiyonun Çağrılma Sayısını Test Etme**

Bir fonksiyonun kaç kez çağrıldığını kontrol etmek için `jest.fn()` kullanarak bir mock fonksiyon oluşturabiliriz.

#### Mock Fonksiyonun Test Edilmesi:
```javascript
test('calls the function twice', () => {
  const mockFunction = jest.fn();
  
  mockFunction();
  mockFunction();
  
  expect(mockFunction).toHaveBeenCalledTimes(2); // Fonksiyonun 2 kez çağrıldığını doğrular
});
```

### 8. **Callback Fonksiyonların Test Edilmesi**

Callback fonksiyonları, bileşen içinde belirli bir işlem tamamlandığında çalışır. Bu tür fonksiyonları test etmek için mock fonksiyonlar ve `expect` kullanabiliriz.

#### Callback Testi:
```javascript
function MyComponent({ onClick }) {
  return <button onClick={onClick}>Click Me</button>;
}

test('calls onClick callback', () => {
  const handleClick = jest.fn();
  
  render(<MyComponent onClick={handleClick} />);
  
  fireEvent.click(screen.getByText('Click Me'));
  
  expect(handleClick).toHaveBeenCalledTimes(1); // Callback fonksiyonu bir kez çağrıldı mı?
});
```

### Özet:

- **`useState` ve `useEffect`** gibi hook'ların test edilmesi için genellikle `act()` kullanılır ve durum değişiklikleri simüle edilir.
- Custom hook'lar için `renderHook` kullanarak hook fonksiyonlarını izole edebiliriz.
- Fonksiyonların veya callback'lerin kaç kez çağrıldığını veya doğru çalıştığını test etmek için `jest.fn()` kullanarak mock fonksiyonlar oluşturabiliriz.
- Asenkron işlemler veya API çağrıları için `async/await` ve mock fonksiyonları kullanarak sonuçları kontrol edebiliriz.

Bu örneklerle React hook'larını ve fonksiyonlarını test ederken `expect`'i nasıl kullanabileceğini görmüş oldun.


Evet, React Testing Library ile test yaparken, bileşenleri test etmek için önce bileşeni renderlememiz gerekiyor. Bileşeni renderledikten sonra, DOM üzerinde test işlemlerini gerçekleştiririz. Bileşeni renderledikten sonra, `getBy`, `findBy`, `queryBy` gibi DOM sorgulama fonksiyonlarını kullanarak elemanları bulur ve testlerimizi yaparız.

### Bileşeni Renderleme

React Testing Library'de bir bileşeni test etmeye başlarken genellikle `render()` fonksiyonunu kullanırız. Bu fonksiyon, bileşeni test etmek üzere sanal DOM'a render eder. Ardından `screen` veya render sonucundan dönen metotlarla DOM üzerinde işlemler yapabiliriz.

#### Örnek: Bileşeni Renderleyip Test Etme

```javascript
import { render, screen } from '@testing-library/react';
import MyComponent from './MyComponent';

test('renders MyComponent and checks content', () => {
  // 1. Bileşeni render ediyoruz
  render(<MyComponent />);

  // 2. Render sonrası bileşendeki metni kontrol ediyoruz
  const element = screen.getByText('Hello World');
  
  // 3. Elemanın DOM'da olduğunu doğruluyoruz
  expect(element).toBeInTheDocument();
});
```

### Bileşen Renderleme Adımları:
1. **Render Etme:** Test ettiğimiz bileşeni `render()` fonksiyonu ile render ediyoruz.
   - `render()` fonksiyonu, bileşeni sanal DOM'a yerleştirir ve `screen` veya diğer DOM sorgulama fonksiyonlarıyla elemanları test etmemizi sağlar.
   
2. **DOM Elemanlarını Bulma:** `screen.getByText`, `screen.findByText` gibi metotlarla render edilen bileşenin içinde DOM elemanlarını buluruz.
   - **`getBy`** anında eleman bulur, eğer eleman bulunamazsa hata fırlatır.
   - **`findBy`** asenkron çalışır ve elemanı bulana kadar bekler. Eğer eleman belirli bir sürede bulunamazsa hata atar.
   - **`queryBy`** ise eleman bulunamazsa `null` döner, hata fırlatmaz.

3. **Doğrulama (`expect`)**: Render edilen bileşenin veya DOM elemanlarının doğru olduğunu `expect` ile test ederiz.

#### Daha Karmaşık Bir Örnek:
Bileşende bir buton tıklaması ve durum değişikliği varsa, render işlemiyle birlikte etkileşim testleri yapabiliriz.

```javascript
import { render, screen, fireEvent } from '@testing-library/react';
import Counter from './Counter'; // Bir counter bileşeni

test('increments counter on button click', () => {
  // 1. Bileşeni render ediyoruz
  render(<Counter />);

  // 2. Başlangıçtaki sayacın 0 olduğunu kontrol ediyoruz
  const counter = screen.getByText('Counter: 0');
  expect(counter).toBeInTheDocument();

  // 3. Butona tıklıyoruz
  const button = screen.getByRole('button', { name: /increment/i });
  fireEvent.click(button);

  // 4. Tıklamadan sonra sayacın arttığını kontrol ediyoruz
  const updatedCounter = screen.getByText('Counter: 1');
  expect(updatedCounter).toBeInTheDocument();
});
```

### Özet:
- Bileşeni test etmeye başlamadan önce her zaman `render()` ile render etmemiz gerekir.
- Render edilen bileşenden sonra, `screen` veya diğer DOM sorgulama metotları ile DOM elemanlarını buluruz.
- `expect` ile bileşenlerin ve elemanların beklenen şekilde çalışıp çalışmadığını doğrularız.
- Eğer bileşenler etkileşim içeriyorsa (buton tıklamaları, form gönderimleri gibi), `fireEvent` kullanarak bu olayları tetikleyebiliriz. 

Render işlemi, testlerin temel adımıdır ve sonraki adımlarda yapacağımız tüm test işlemleri render sonrası gerçekleşir.
Evet, **`useEffect`** hook'unu kullanan bileşenleri test etmek için de aynı şekilde önce bileşeni **render** etmemiz gerekir. `useEffect`, bileşen render edildiğinde yan etkileri (örneğin, API çağrıları, DOM manipülasyonları veya zamanlayıcılar) tetikleyen bir hook'tur. Bu nedenle, bir bileşen `useEffect` içeriyorsa, bileşeni render ettikten sonra `useEffect`'in çalışıp çalışmadığını kontrol edebiliriz.

`useEffect` ile asenkron işlemler veya yan etkiler olduğu için genellikle `jest.fn()` gibi mock fonksiyonlar ve asenkron test yöntemleri kullanılır. İşte adımlar:

### 1. Bileşeni Render Ediyoruz
- Bileşeni `render` fonksiyonu ile render ediyoruz.

### 2. `useEffect` İçindeki İşlemleri Test Etmek
- `useEffect` içinde API çağrısı gibi yan etkileri tetikleyebiliriz.
- Mock fonksiyonlarla bu yan etkileri kontrol edebiliriz (örneğin, `fetch` veya diğer asenkron işlemleri).

### 3. Sonuçları Doğrulamak
- `useEffect`'in tetiklediği değişiklikleri DOM'da kontrol edebiliriz.

### `useEffect` İçeren Bir Bileşenin Testi

#### Senaryo: API'den veri çeken bir bileşenimiz var.
```javascript
import { render, screen, waitFor } from '@testing-library/react';
import MyComponent from './MyComponent';

// Mock bir API çağrısı
global.fetch = jest.fn(() =>
  Promise.resolve({
    json: () => Promise.resolve({ message: 'Hello World' })
  })
);

test('fetches and displays data', async () => {
  // 1. Bileşeni render ediyoruz
  render(<MyComponent />);

  // 2. API çağrısı yapılmadan önce "Loading..." mesajını kontrol ediyoruz
  expect(screen.getByText('Loading...')).toBeInTheDocument();

  // 3. API çağrısından sonra DOM'un doğru güncellenmesini bekliyoruz
  const data = await waitFor(() => screen.getByText('Hello World'));

  // 4. Verinin DOM'da göründüğünü doğruluyoruz
  expect(data).toBeInTheDocument();

  // 5. API'nin bir kez çağrıldığını doğruluyoruz
  expect(fetch).toHaveBeenCalledTimes(1);
});
```

### Açıklama:
- **Mock API**: Bu örnekte, global `fetch` fonksiyonunu `jest.fn()` ile mock'ladık. Bileşenimiz `useEffect` ile bir API çağrısı yaptığında, bu mock fonksiyon çağrılır ve test ortamında veri döner.
- **Render Etme**: Bileşeni `render` fonksiyonu ile test ortamına render ettik.
- **Loading Mesajı**: Bileşen render edilir edilmez, `useEffect` çağrısı yapılmadan önce, "Loading..." metninin DOM'da olduğunu kontrol ettik.
- **Verinin Yüklenmesi**: `useEffect` ile veri yüklendikten sonra, DOM'da bu verinin doğru şekilde gösterildiğini kontrol ettik (API'den gelen "Hello World" mesajı).
- **Asenkron Test**: API çağrısı asenkron olduğundan, verinin DOM'a eklenmesini `waitFor` fonksiyonu ile bekledik.

### Zamanlayıcıları Kullanan `useEffect` İçin Test

Bir başka yaygın senaryo, `useEffect` içinde zamanlayıcılar (örneğin, `setTimeout`, `setInterval`) kullanmaktır. Bu tür testlerde Jest'in zamanlayıcı fonksiyonlarını mock'layarak, testleri hızlandırabiliriz.

#### Senaryo: Bileşen 1 saniye sonra bir mesaj gösteriyor.
```javascript
import { render, screen, act } from '@testing-library/react';
import MyComponent from './MyComponent';

jest.useFakeTimers();

test('displays message after 1 second', () => {
  // 1. Bileşeni render ediyoruz
  render(<MyComponent />);

  // 2. Başlangıçta mesajın olmadığını kontrol ediyoruz
  expect(screen.queryByText('Hello after 1 second')).toBeNull();

  // 3. Zamanı 1 saniye ileri alıyoruz
  act(() => {
    jest.advanceTimersByTime(1000); // 1 saniyeyi hızla ileri al
  });

  // 4. 1 saniye sonra mesajın DOM'da olduğunu doğruluyoruz
  expect(screen.getByText('Hello after 1 second')).toBeInTheDocument();
});
```

### Açıklama:
- **`jest.useFakeTimers()`**: Jest zamanlayıcıları taklit eder, bu sayede test sırasında zamanın hızlıca ileri alınmasını sağlar.
- **`act()`**: Jest zamanlayıcıları ile ilgili tüm işlemler `act()` içinde olmalıdır. `act()`, React bileşenlerinin yan etkilerinin doğru çalışmasını sağlar.
- **`jest.advanceTimersByTime()`**: Bu fonksiyon ile zamanlayıcıları hızlandırır ve 1 saniyeyi ileri alırız.

### `useEffect` ile Bir Cleanup Fonksiyonu Test Etmek
Bileşenlerde kullanılan `useEffect` cleanup fonksiyonları (örneğin, zamanlayıcıları temizlemek) de test edilebilir.

#### Senaryo: Bileşen unmount edilmeden önce zamanlayıcıyı temizleyen bir `useEffect`:
```javascript
import { render, screen, act } from '@testing-library/react';
import MyComponent from './MyComponent';

jest.useFakeTimers();

test('cleans up timer on unmount', () => {
  const { unmount } = render(<MyComponent />);

  // Zamanı 1 saniye ileri alıyoruz
  act(() => {
    jest.advanceTimersByTime(1000);
  });

  // Zamanlayıcının doğru çalıştığını kontrol edelim
  expect(screen.getByText('Timer Finished')).toBeInTheDocument();

  // Bileşeni unmount ediyoruz
  unmount();

  // Zamanlayıcının iptal edildiğini doğrulamak için jest'in mock'larını kontrol edelim
  expect(clearTimeout).toHaveBeenCalledTimes(1); // Timer temizlendi mi?
});
```

### Özet:
- **`useEffect`** kullanan bileşenler test edilirken, bileşeni **render** etmek gerekir. `useEffect` tetiklendikten sonra yan etkileri test etmek için **asenkron test yöntemleri** kullanılır.
- Mock fonksiyonlar ile API çağrıları veya zamanlayıcılar gibi yan etkiler simüle edilebilir.
- **`jest.useFakeTimers()`** ve **`act()`** gibi Jest'in sunduğu özel fonksiyonlarla zamanlayıcıları test edebilir ve cleanup işlemlerini doğrulayabiliriz.

Bu yöntemlerle `useEffect` hook'unun tetiklediği her türlü asenkron işlem veya yan etkileri test edebilirsin.

Eğer bir **API çağrısı** yapıyorsak ve back-end'den bir veri çekiyorsak (örneğin `name` ve `surname` verileri), bu çağrıyı test etmek için birkaç adımda ilerleyebiliriz. Test sırasında API'yi gerçek bir çağrı yapmak yerine **mock** ederek, test ortamında bu veri çağrısını simüle edebiliriz.

Aşağıda, **API çağrısını** ve bileşene gelen `name` ve `surname` verilerini test etmek için bir örnek veriyorum:

### Senaryo: 
Bir bileşenimiz var, bileşen back-end'den `name` ve `surname` verilerini çekiyor ve ekrana yazdırıyor.

### Bileşen Kodu (`UserInfo.js`):
```javascript
import React, { useEffect, useState } from 'react';

function UserInfo() {
  const [user, setUser] = useState(null);

  useEffect(() => {
    // API çağrısı
    async function fetchUserData() {
      const response = await fetch('/api/user');
      const data = await response.json();
      setUser(data);
    }

    fetchUserData();
  }, []);

  if (!user) return <div>Loading...</div>;

  return (
    <div>
      <h1>{user.name}</h1>
      <h2>{user.surname}</h2>
    </div>
  );
}

export default UserInfo;
```

### Test Kodu (`UserInfo.test.js`):

Bu testte API çağrısını **mock** edeceğiz ve bileşenin back-end'den gelen veriyi doğru şekilde ekrana yazdırıp yazdırmadığını test edeceğiz.

```javascript
import { render, screen, waitFor } from '@testing-library/react';
import UserInfo from './UserInfo';

// Mock API çağrısı
global.fetch = jest.fn(() =>
  Promise.resolve({
    json: () => Promise.resolve({
      name: 'John',
      surname: 'Doe'
    })
  })
);

test('fetches and displays user info', async () => {
  // 1. Bileşeni render ediyoruz
  render(<UserInfo />);

  // 2. API çağrısı tamamlanmadan önce "Loading..." mesajını kontrol ediyoruz
  expect(screen.getByText('Loading...')).toBeInTheDocument();

  // 3. API'den gelen veriyi ekranda bekliyoruz
  const nameElement = await waitFor(() => screen.getByText('John'));
  const surnameElement = await waitFor(() => screen.getByText('Doe'));

  // 4. Verinin DOM'da gösterildiğini doğruluyoruz
  expect(nameElement).toBeInTheDocument();
  expect(surnameElement).toBeInTheDocument();

  // 5. API çağrısının bir kez yapıldığını doğruluyoruz
  expect(fetch).toHaveBeenCalledTimes(1);
});
```

### Açıklama:

1. **Mock API Çağrısı:**
   - `global.fetch` fonksiyonunu `jest.fn()` ile mock'ladık ve dönen veriyi manuel olarak `name: 'John', surname: 'Doe'` olarak ayarladık. Gerçek bir API çağrısı yerine, test ortamında bu veriyi simüle ediyoruz.
   
2. **Render Etme:**
   - `render(<UserInfo />)` fonksiyonu ile bileşeni test ortamına render ettik.

3. **Loading Durumu:**
   - Bileşen render edildiğinde `useEffect` hemen çalışacak ve API çağrısını yapacak. Bu sırada "Loading..." mesajının DOM'da olduğunu doğruladık.

4. **Veri Yüklenmesi:**
   - `waitFor()` fonksiyonu ile API çağrısından gelen veriyi bekledik ve `name` ve `surname` bilgilerini DOM'da olup olmadığını kontrol ettik.
   - `waitFor`, asenkron işlemler için kullanılır ve elemanın DOM'da görünmesini bekler.

5. **API Çağrısı Doğrulama:**
   - `expect(fetch).toHaveBeenCalledTimes(1)` ile `fetch` fonksiyonunun bir kez çağrıldığını doğruladık.

### API Çağrısı Başarısız Olduğunda Test Etme

API çağrısının başarısız olduğu durumları da test edebilirsin. Örneğin, eğer API çağrısı başarısız olursa, bileşen bir hata mesajı gösterebilir.

#### Senaryo: API çağrısı başarısız olduysa, "Hata oluştu" mesajı gösteriliyor.

### Bileşen (`UserInfo.js`):
```javascript
function UserInfo() {
  const [user, setUser] = useState(null);
  const [error, setError] = useState(false);

  useEffect(() => {
    async function fetchUserData() {
      try {
        const response = await fetch('/api/user');
        const data = await response.json();
        setUser(data);
      } catch (error) {
        setError(true);
      }
    }

    fetchUserData();
  }, []);

  if (error) return <div>Error occurred</div>;
  if (!user) return <div>Loading...</div>;

  return (
    <div>
      <h1>{user.name}</h1>
      <h2>{user.surname}</h2>
    </div>
  );
}

export default UserInfo;
```

### Test Kodu (`UserInfo.test.js`):
```javascript
test('displays error message on API failure', async () => {
  // Mock API başarısız oluyor
  global.fetch = jest.fn(() =>
    Promise.reject('API failure')
  );

  // Bileşeni render ediyoruz
  render(<UserInfo />);

  // API çağrısından önce "Loading..." mesajını kontrol ediyoruz
  expect(screen.getByText('Loading...')).toBeInTheDocument();

  // Hata mesajını bekliyoruz
  const errorMessage = await waitFor(() => screen.getByText('Error occurred'));

  // Hata mesajının DOM'da olup olmadığını doğruluyoruz
  expect(errorMessage).toBeInTheDocument();
});
```

### Açıklama:
- Bu senaryoda, API çağrısı `Promise.reject()` ile başarısız oluyor.
- `useEffect` içinde `catch` bloğuyla hatayı yakalıyor ve `error` durumunu `true` yapıyoruz.
- Test sırasında hata mesajının DOM'da görünüp görünmediğini kontrol ediyoruz.

Bu yapıyla API çağrısı yapan bileşenlerin hem başarılı hem de başarısız durumlarını kolayca test edebilirsin.
￼
￼

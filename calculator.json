const display = document.getElementById('display');
const buttons = document.querySelectorAll('button[data-value]');

buttons.forEach(button => {
  button.addEventListener('click', () => {
    const value = button.getAttribute('data-value');
    handleInput(value);
  });
});

document.addEventListener('keydown', (e) => {
  const key = e.key;
  if ('0123456789+-*/.=()'.includes(key)) {
    handleInput(key);
  } else if (key === 'Enter') {
    handleInput('=');
  } else if (key === 'Backspace') {
    handleInput('←');
  } else if (key.toLowerCase() === 'c') {
    handleInput('C');
  }
});

function handleInput(value) {
  if (value === 'C') {
    display.value = '';
  } else if (value === '←') {
    display.value = display.value.slice(0, -1);
  } else if (value === '=') {
    try {
      const result = eval(display.value);
      display.value = result;
    } catch {
      display.value = 'Error';
    }
  } else {
    display.value += value;
  }
}
